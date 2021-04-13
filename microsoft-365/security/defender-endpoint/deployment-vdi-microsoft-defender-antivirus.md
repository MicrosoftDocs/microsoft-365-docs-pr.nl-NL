---
title: Implementatiehandleiding voor Microsoft Defender Antivirus Virtual Desktop Infrastructure
description: Lees hoe u Microsoft Defender Antivirus implementeert in een virtuele bureaubladomgeving voor de beste balans tussen beveiliging en prestaties.
keywords: vdi, hyper-v, vm, virtual machine, windows defender, antivirus, av, virtual desktop, rds, remote desktop
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b81addbcaabb1c5ea0d344dbaab9d76a8b100c2b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690720"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Implementatiehandleiding voor Microsoft Defender Antivirus in een VDI-omgeving (Virtual Desktop Infrastructure)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Naast standaard on-premises of hardwareconfiguraties kunt u ook Microsoft Defender Antivirus gebruiken in een extern bureaublad (RDS) of VDI-omgeving (Virtual Desktop Infrastructure).

Zie [Documentatie over Windows Virtual Desktop voor](/azure/virtual-desktop) meer informatie over Microsoft Remote Desktop Services en VDI-ondersteuning.

Zie [Endpoint Protection](/azure/security-center/security-center-install-endpoint-protection)installeren in Azure Defender voor virtuele azure-machines.

Met de mogelijkheid om eenvoudig updates te implementeren voor VM's die worden uitgevoerd in VDI's, hebben we deze handleiding ingekort om ons te concentreren op hoe u snel en eenvoudig updates op uw machines kunt krijgen. U hoeft geen gouden afbeeldingen meer periodiek te maken en te verzegelen, aangezien updates worden uitgebreid naar de onderdelen op de hostserver en vervolgens rechtstreeks naar de VM worden gedownload wanneer deze is ingeschakeld.

In deze handleiding wordt beschreven hoe u uw VM's kunt configureren voor optimale beveiliging en prestaties, inclusief het volgende:

- [Een speciale VDI-bestands delen instellen voor beveiligingsinformatieupdates](#set-up-a-dedicated-vdi-file-share)
- [Geplande scans willekeurig maken](#randomize-scheduled-scans)
- [Snelle scans gebruiken](#use-quick-scans)
- [Meldingen voorkomen](#prevent-notifications)
- [Scans uitschakelen na elke update](#disable-scans-after-an-update)
- [Verouderd machines of machines scannen die al een tijdje offline zijn](#scan-vms-that-have-been-offline)
- [Uitsluitingen toepassen](#exclusions)

U kunt ook het whitepaper [Microsoft Defender Antivirus](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf)downloaden op virtual desktop-infrastructuur, waarin wordt ge kijkt naar de nieuwe functie voor het bijwerken van gedeelde beveiligingsinformatie, naast prestatietests en richtlijnen voor het testen van antivirusprestaties op uw eigen VDI.

> [!IMPORTANT]
> Hoewel VDI kan worden gehost op Windows Server 2012 of Windows Server 2016, moeten op de virtuele machines (VM's) minimaal Windows 10, 1607 worden uitgevoerd vanwege verbeterde beveiligingstechnologieën en -functies die niet beschikbaar zijn in eerdere versies van Windows.<br/>Er zijn prestatie- en functieverbeteringen in de manier waarop Microsoft Defender AV werkt op virtuele machines in Windows 10 Insider Preview, build 18323 (en hoger). We identificeren in deze handleiding of u een Insider Preview-build wilt gebruiken. als dit niet is opgegeven, is Windows 10 1607 de minimaal vereiste versie voor de beste beveiliging en prestaties.

## <a name="set-up-a-dedicated-vdi-file-share"></a>Een speciale VDI-bestands delen instellen

In Windows 10, versie 1903, hebben we de functie voor gedeelde beveiligingsinformatie geïntroduceerd, waarmee het uitpakken van gedownloade beveiligingsintelligentie-updates wordt uitgeschakeld op een hostmachine, waardoor eerdere CPU-, schijf- en geheugenresources op afzonderlijke machines worden opgeslagen. Deze functie is backported en werkt nu in Windows 10 versie 1703 en hoger. U kunt deze functie instellen met een groepsbeleid of PowerShell.

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a>Groepsbeleid gebruiken om de functie voor gedeelde beveiligingsinformatie in te stellen:

1. Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik vervolgens op **Bewerken.**

2. Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

3. Klik **op Beheersjablonen.**

4. Vouw de structuur uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Security Intelligence  >  **Updates**.

5. Dubbelklik op **Locatie voor beveiligingsinformatie definiëren voor VDI-clients** en stel de optie in op **Ingeschakeld.** Er wordt automatisch een veld weergegeven.

6. Enter (zie Downloaden en uitpakken voor hulp bij `\\<sharedlocation\>\wdav-update` [deze waarde).](#download-and-unpackage-the-latest-updates)

7. Klik op **OK**.

8. Implementeer het GPO naar de VM's die u wilt testen.

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a>PowerShell gebruiken om de functie voor gedeelde beveiligingsinformatie in te stellen

Gebruik de volgende cmdlet om de functie in te stellen. U moet dit vervolgens pushen omdat u normaal gesproken configuratiebeleid op basis van PowerShell naar de VM's zou pushen:

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

Zie de [sectie Downloaden en uitpakken](#download-and-unpackage-the-latest-updates) voor wat \<shared location\> het wordt.

## <a name="download-and-unpackage-the-latest-updates"></a>De nieuwste updates downloaden en uitpakken

Nu kunt u aan de slag met het downloaden en installeren van nieuwe updates. Hieronder hebben we een voorbeeldscript voor PowerShell voor u gemaakt. Dit script is de eenvoudigste manier om nieuwe updates te downloaden en ze klaar te maken voor uw VM's. Vervolgens moet u instellen dat het script op een bepaald moment op de beheermachine wordt uitgevoerd met behulp van een geplande taak (of, als u bekend bent met het gebruik van PowerShell-scripts in Azure, Intune of SCCM, kunt u deze scripts ook gebruiken).

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

U kunt instellen dat een geplande taak eenmaal per dag wordt uitgevoerd, zodat wanneer het pakket wordt gedownload en uitgepakt, de VM's de nieuwe update ontvangen. We raden u aan om één keer per dag te beginnen, maar u moet experimenteren met het verhogen of verlagen van de frequentie om de impact te begrijpen. 

Beveiligingsinformatiepakketten worden meestal eenmaal per drie tot vier uur gepubliceerd. Het is niet raadzaam een frequentie in te stellen die korter is dan vier uur, omdat hierdoor de overhead van het netwerk op uw beheerapparaat zonder voordeel wordt vergroot.

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a>Een geplande taak instellen om het PowerShell-script uit te voeren

1. Open op de beheermachine het menu Start en typ **Taakplanning.** Open deze en selecteer **Taak maken...** op het zijpaneel.

2. Voer de naam in als **Beveiligingsinformatie-uitpakken.** Ga naar het **tabblad Trigger.** Selecteer **Nieuw...** > **Dagelijks** en selecteer **OK.**

3. Ga naar het **tabblad** Acties. Selecteer **Nieuw...** Voer **PowerShell** in het **veld Programma/script** in. Voer `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` in het veld Argumenten **toevoegen** in. Kies **OK**.

4. U kunt er indien nodig voor kiezen om extra instellingen te configureren.

5. Selecteer **OK** om de geplande taak op te slaan.
 
U kunt de update handmatig starten door met de rechtermuisknop op de taak te klikken en op **Uitvoeren te klikken.**

### <a name="download-and-unpackage-manually"></a>Handmatig downloaden en uitpakken

Als u alles liever handmatig wilt doen, gaat u als volgende te werk om het gedrag van het script te repliceren:

1. Maak een nieuwe map in de systeemwortel die wordt genoemd om intelligence-updates op te `wdav_update` slaan, bijvoorbeeld om de map te `c:\wdav_update` maken.

2. Een submap maken onder *wdav_update* met een GUID-naam, zoals `{00000000-0000-0000-0000-000000000000}`

Hier is een voorbeeld: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`

   > [!NOTE]
   > In het script hebben we het zo ingesteld dat de laatste 12 cijfers van de GUID het jaar, de maand, de dag en de tijd zijn waarop het bestand is gedownload, zodat er telkens een nieuwe map wordt gemaakt. U kunt dit wijzigen zodat het bestand telkens naar dezelfde map wordt gedownload.

3. Download een beveiligingsinformatiepakket [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  in de map GUID. Het bestand moet een naam `mpam-fe.exe` hebben.

4. Open een cmd-promptvenster en ga naar de MAP GUID die u hebt gemaakt. Gebruik bijvoorbeeld **de opdracht /X-extractie** om de bestanden op te `mpam-fe.exe /X` halen.

   > [!NOTE]
   > De VM's nemen het bijgewerkte pakket op wanneer een nieuwe GUID-map wordt gemaakt met een uitgepakt updatepakket of wanneer een bestaande map wordt bijgewerkt met een nieuw uitgepakt pakket.

## <a name="randomize-scheduled-scans"></a>Geplande scans willekeurig maken

Geplande scans worden uitgevoerd naast [realtime beveiliging en scannen.](configure-real-time-protection-microsoft-defender-antivirus.md)

De begintijd van de scan zelf is nog steeds gebaseerd op het geplande scanbeleid **(ScheduleDay,** **ScheduleTime** en **ScheduleQuickScanTime).** Randomization will cause Microsoft Defender Antivirus to start a scan on each machine within a 4 hour window from the time set for the scheduled scan.

Zie [Scans plannen](scheduled-catch-up-scans-microsoft-defender-antivirus.md) voor andere configuratieopties die beschikbaar zijn voor geplande scans.

## <a name="use-quick-scans"></a>Snelle scans gebruiken

U kunt het type scan opgeven dat moet worden uitgevoerd tijdens een geplande scan. Snelle scans zijn de voorkeursbenadering omdat ze zijn ontworpen om te zoeken op alle plaatsen waar malware moet staan om actief te zijn. In de volgende procedure wordt beschreven hoe u snelle scans kunt instellen met groepsbeleid.

1. Ga in de Groepsbeleidseditor naar **Beheersjablonen**  >  **Windows-onderdelen**  >  **Microsoft Defender Antivirus**  >  **Scan.**

2. Selecteer **Geef het scantype op dat u wilt gebruiken** voor een geplande scan en bewerk vervolgens de beleidsinstelling.

3. Stel het beleid in **op Ingeschakeld** en selecteer onder **Opties** de optie **Snel scannen.**

4. Kies **OK**. 

5. Implementeer het groepsbeleidsobject zoals u gewoonlijk doet.

## <a name="prevent-notifications"></a>Meldingen voorkomen

Soms kunnen Microsoft Defender Antivirusmeldingen worden verzonden naar of blijven bestaan in meerdere sessies. Als u dit probleem wilt minimaliseren, kunt u de gebruikersinterface van Microsoft Defender Antivirus vergrendelen. In de volgende procedure wordt beschreven hoe u meldingen met groepsbeleid kunt onderdrukken.

1. Ga in de Groepsbeleidseditor naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Client  >  **Interface.**

2. Selecteer **Alle meldingen onderdrukken en** bewerk vervolgens de beleidsinstellingen. 

3. Stel het beleid in **op Ingeschakeld** en selecteer **OK.**

4. Implementeer het groepsbeleidsobject zoals u gewoonlijk doet.

Als u meldingen onderdrukt, worden meldingen van Microsoft Defender Antivirus niet weergegeven in het Actiecentrum in Windows 10 wanneer scans worden uitgevoerd of herstelacties worden uitgevoerd. Het beveiligingsteam ziet echter de resultaten van de scan in het Microsoft Defender-beveiligingscentrum [https://securitycenter.windows.com](https://securitycenter.windows.com) ().

> [!TIP]
> Als u het Actiecentrum in Windows 10 wilt openen, gaat u als volgt te werk:
> - Selecteer het pictogram Actiecentrum aan de rechterkant van de taakbalk.
> - Druk op de knop Windows-logotoets + A.
> - Swipe op een touchscreen vanaf de rechterrand van het scherm.

## <a name="disable-scans-after-an-update"></a>Scans uitschakelen na een update

Als u een scan na een update uit kunt uitschakelen, wordt voorkomen dat er een scan wordt uitgevoerd na ontvangst van een update. U kunt deze instelling toepassen bij het maken van de basisafbeelding als u ook een snelle scan hebt uitgevoerd. Op deze manier kunt u voorkomen dat de onlangs bijgewerkte VM opnieuw een scan kan uitvoeren (zoals u al hebt gescand toen u de basisafbeelding maakte).

> [!IMPORTANT]
> Met scans na een update kunt u ervoor zorgen dat uw VM's worden beveiligd met de meest recente beveiligingsinformatie-updates. Als u deze optie uitkeert, wordt het beveiligingsniveau van uw VM's beperkt en mag deze alleen worden gebruikt wanneer u eerst de basisafbeelding maakt of implementeert.

1. Ga in de Groepsbeleidseditor naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Security Intelligence  >  **Updates.**

2. Selecteer **Scannen in-/uit-/uit-2014** en bewerk vervolgens de beleidsinstelling.

3. Stel het beleid in op **Uitgeschakeld.**

4. Kies **OK**.

5. Implementeer het groepsbeleidsobject zoals u gewoonlijk doet.

Met dit beleid wordt voorkomen dat een scan direct na een update wordt uitgevoerd.

## <a name="scan-vms-that-have-been-offline"></a>VM's scannen die offline zijn

1. Ga in de Groepsbeleidseditor naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus**  >  **Scan.**

2. Selecteer **Inhaal quick scan in- en uithalen** en bewerk vervolgens de beleidsinstelling.

3. Stel het beleid in op **Ingeschakeld.**

4. Kies **OK**.

5. Implementeer het groepsbeleidsobject zoals u gewoonlijk doet.

Dit beleid dwingt een scan af als de VM twee of meer opeenvolgende geplande scans heeft gemist.

## <a name="enable-headless-ui-mode"></a>Gebruikersinterface zonder hoofd inschakelen

1. Ga in de Groepsbeleidseditor naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Client  >  **Interface.**

2. Selecteer **De gebruikersinterfacemodus zonder hoofd inschakelen** en bewerk het beleid.

3. Stel het beleid in op **Ingeschakeld.**

4. Klik op **OK**.

5. Implementeer het groepsbeleidsobject zoals u gewoonlijk doet.
 
Met dit beleid wordt de volledige gebruikersinterface van Microsoft Defender Antivirus verborgen voor eindgebruikers in uw organisatie.

## <a name="exclusions"></a>Uitsluitingen

Uitsluitingen kunnen worden toegevoegd, verwijderd of aangepast aan uw behoeften.

Zie Microsoft [Defender Antivirus exclusions configureren op Windows Server voor meer informatie.](configure-exclusions-microsoft-defender-antivirus.md)

## <a name="additional-resources"></a>Aanvullende bronnen

- [Tech Community Blog: Microsoft Defender Antivirus configureren voor niet-permanente VDI-machines](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [TechNet-forums op Remote Desktop Services en VDI](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [SignatureDownloadCustomTask PowerShell-script](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)