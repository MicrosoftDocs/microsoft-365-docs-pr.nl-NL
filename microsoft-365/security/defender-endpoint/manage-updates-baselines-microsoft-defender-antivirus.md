---
title: Updates Microsoft Defender Antivirus en basislijnen toepassen
description: Beheer hoe Microsoft Defender Antivirus beveiligings- en productupdates ontvangt.
keywords: updates, beveiligingslijnlijnen, beveiliging, planningsupdates, force-updates, mobiele updates, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 06/14/2021
ms.openlocfilehash: 1c7ff52398e048aa34fd9c5ab3d8edd1004ea5ec
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929441"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a>Updates Microsoft Defender Antivirus en basislijnen toepassen

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender Antivirus

Het Microsoft Defender Antivirus up-to-date houden is essentieel om ervoor te zorgen dat uw apparaten de nieuwste technologie en functies hebben die nodig zijn om te beschermen tegen nieuwe malware en aanvalstechnieken. Zorg ervoor dat u uw antivirusbeveiliging bij werkt, zelfs als Microsoft Defender Antivirus actief is in [de passieve modus.](microsoft-defender-antivirus-compatibility.md) Er zijn twee soorten updates die betrekking hebben op het up-to-date Microsoft Defender Antivirus houden:

- Beveiligingsintelligentie-updates
- Productupdates

> [!TIP]
> Als u de meest recente engine, platform en handtekeningdatum wilt zien, gaat u naar de beveiligingsinformatieupdates voor Microsoft Defender Antivirus [en andere Microsoft-antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)

## <a name="security-intelligence-updates"></a>Beveiligingsintelligentie-updates

Microsoft Defender Antivirus gebruikt beveiliging in de cloud (ook wel de Microsoft Advanced Protection Service of KAARTEN genoemd) en downloadt regelmatig [beveiligingsinformatie-updates](cloud-protection-microsoft-defender-antivirus.md) om bescherming te bieden.

> [!NOTE]
> Updates worden uitgebracht onder de onderstaande KB-nummers:  
> - Microsoft Defender Antivirus: KB2267602  
> - System Center Endpoint Protection: KB2461484

Beveiliging in de cloud is altijd actief en hiervoor is een actieve verbinding met internet vereist. Beveiligingsintelligentie-updates vinden plaats op een geplande cadans (configureerbaar via beleid). Zie Microsoft [Cloud-beveiliging](cloud-protection-microsoft-defender-antivirus.md)gebruiken in Microsoft Defender Antivirus voor meer Microsoft Defender Antivirus. 

Zie Beveiligingsinformatie-updates voor Microsoft Defender Antivirus en andere Microsoft-antimalware voor een lijst met recente [beveiligingsinformatieupdates.](https://www.microsoft.com/en-us/wdsi/defenderupdates)

Engine-updates worden opgenomen in beveiligingsinformatie-updates en worden maandelijks uitgebracht.

## <a name="product-updates"></a>Productupdates

Microsoft Defender Antivirus vereist [maandelijkse updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (ook wel *platformupdates* genoemd) en ontvangen belangrijke functieupdates naast Windows 10 releases.

U kunt de distributie van updates beheren via een van de volgende methoden: 

- [Windows Serverupdateservice (WSUS)](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/sum/understand/software-updates-introduction)
- De gebruikelijke methode die u gebruikt om Microsoft te implementeren en Windows te installeren op eindpunten in uw netwerk.

Zie De bronnen voor [beveiligingsupdates Microsoft Defender Antivirus beheren voor meer informatie.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)

> [!NOTE]
> Maandelijkse updates worden gefaseerd uitgebracht, wat resulteert in meerdere pakketten die zichtbaar zijn in [uw Window Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)

## <a name="monthly-platform-and-engine-versions"></a>Maandelijkse platform- en engineversies

Zie Update voor Windows Defender [antimalwareplatform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)voor informatie over het bijwerken of installeren van de platformupdate.

Al onze updates bevatten 
- prestatieverbeteringen;
- verbeteringen in de servicebaarheid; en 
- integratieverbeteringen (Cloud, [Microsoft 365 Defender).](/microsoft-365/security/defender/microsoft-365-defender)
<br/><br/>
<details>
<summary> Mei-2021 (Platform: 4.18.2105.4 | Motor: 1.1.18200.4)</summary>

&ensp;Versie van beveiligingsinformatieupdate: **1.341.8.0**  
&ensp;Uitgebracht: **3 juni 2021**  
&ensp;Platform: **4.18.2105.4**  
&ensp;Motor: **1.1.18200.4**  
&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**
    
### <a name="whats-new"></a>Wat is er nieuw
- Verbeteringen in [gedragscontrole](client-behavioral-blocking.md) 
- Functie [voor het filteren van meldingen](network-protection.md) voor vaste netwerkbeveiliging

### <a name="known-issues"></a>Bekende problemen
Geen bekende problemen  
<br/>
</details><details>
<summary> April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</summary>

&ensp;Versie van beveiligingsinformatieupdate: **1.337.2.0**  
&ensp;Uitgebracht: **26 april 2021**  (Engine: 1.1.18100.6 uitgebracht op 5 mei 2021) &ensp; Platform: **4.18.2104.14**  
&ensp;Motor: **1.1.18100.5**  
&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**
    
### <a name="whats-new"></a>Wat is er nieuw
- Aanvullende logica voor gedragscontrole
- Verbeterde detectie van keylogger in de kernelmodus

### <a name="known-issues"></a>Bekende problemen
Geen bekende problemen  
<br/>
</details><details>
<summary> Maart-2021 (Platform: 4.18.2103.7 | Motor: 1.1.18000.5)</summary>

&ensp;Versie van beveiligingsinformatieupdate: **1.335.36.0**  
&ensp;Uitgebracht: **2 april 2021**  
&ensp;Platform: **4.18.2103.7**  
&ensp;Motor: **1.1.18000.5**  
&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**
    
### <a name="whats-new"></a>Wat is er nieuw

- Verbetering van de engine Gedragscontrole 
- Uitgebreide netwerkbeperking met brute-force-attack 
- Extra mislukte poging tot het maken van een poging tot geknoei wanneer [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is ingeschakeld

### <a name="known-issues"></a>Bekende problemen
Geen bekende problemen  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a>Eerdere versieupdates: Alleen ondersteuning voor technische upgrade

Nadat een nieuwe pakketversie is uitgebracht, wordt de ondersteuning voor de vorige twee versies beperkt tot alleen technische ondersteuning. Versies die ouder zijn dan die in deze sectie worden weergegeven, en alleen beschikbaar zijn voor ondersteuning voor technische upgrades. 
<br/><br/>
<details>
<summary> Februari-2021 (Platform: 4.18.2102.3 | Motor: 1.1.17900.7)</summary>

&ensp;Versie van beveiligingsinformatieupdate: **1.333.7.0**  
&ensp;Uitgebracht: **9 maart 2021**  
&ensp;Platform: **4.18.2102.3**  
&ensp;Motor: **1.1.17900.7**  
&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**
    
### <a name="whats-new"></a>Wat is er nieuw

- Verbeterde serviceherstel door middel [van beveiliging tegen geknoei](prevent-changes-to-security-settings-with-tamper-protection.md)
- Beveiligingsbereik voor tampers uitbreiden

### <a name="known-issues"></a>Bekende problemen
Geen bekende problemen  
<br/>
</details><details>
<summary> Januari-2021 (Platform: 4.18.2101.9 | Motor: 1.1.17800.5)</summary>

&ensp;Versie van beveiligingsinformatieupdate: **1.327.1854.0**  
&ensp;Uitgebracht: **2 februari 2021**  
&ensp;Platform: **4.18.2101.9**  
&ensp;Motor: **1.1.17800.5**  
&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**
    
### <a name="whats-new"></a>Wat is er nieuw

- Verbeteringen voor detectie van Shellcode-exploits
- Meer zichtbaarheid voor pogingen tot het stelen van referenties
- Verbeteringen in antitamperingfuncties in Microsoft Defender Antivirus services
- Verbeterde ondersteuning voor ARM x64-emulatie
- Oplossing: EDR Blokkeermelding blijft in de bedreigingsgeschiedenis staan nadat realtimebeveiliging eerste detectie heeft uitgevoerd

### <a name="known-issues"></a>Bekende problemen
Geen bekende problemen  
<br/>
</details><details>
<summary> November-2020 (Platform: 4.18.2011.6 | Motor: 1.1.17700.4)</summary>

&ensp;Versie van beveiligingsinformatieupdate: **1.327.1854.0**  
&ensp;Uitgebracht: **3 december 2020**  
&ensp;Platform: **4.18.2011.6**  
&ensp;Motor: **1.1.17700.4**  
&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**
    
### <a name="whats-new"></a>Wat is er nieuw

- Verbeterde [ondersteuning voor SmartScreen-statusregistratie](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

### <a name="known-issues"></a>Bekende problemen
Geen bekende problemen  
<br/>
</details><details>
<summary> Oktober-2020 (Platform: 4.18.2010.7 | Motor: 1.1.17600.5)</summary>

&ensp;Versie van beveiligingsinformatieupdate: **1.327.7.0**  
&ensp;Uitgebracht: **29 oktober 2020**  
&ensp;Platform: **4.18.2010.7**  
&ensp;Motor: **1.1.17600.5**  
&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**
    
### <a name="whats-new"></a>Wat is er nieuw

- Nieuwe beschrijvingen voor categorieën met speciale bedreigingen
- Verbeterde emulatiemogelijkheden
- Verbeterde mogelijkheden voor het toestaan/blokkeren van hostadressen
- Nieuwe optie in Defender CSP om het samenvoegen van lokale gebruikersuitsluitingen te negeren

### <a name="known-issues"></a>Bekende problemen

Geen bekende problemen  
<br/>
</details><details>
<summary> September-2020 (Platform: 4.18.2009.7 | Motor: 1.1.17500.4)</summary>

&ensp;Versie van beveiligingsinformatieupdate: **1.325.10.0**  
&ensp;Uitgebracht: **1 oktober 2020**  
&ensp;Platform: **4.18.2009.7**  
&ensp;Motor: **1.1.17500.4**  
&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**
    
### <a name="whats-new"></a>Wat is er nieuw

- Beheerdersmachtigingen zijn vereist om bestanden in quarantaine te herstellen
- XML-opgemaakte gebeurtenissen worden nu ondersteund
- CSP-ondersteuning voor het negeren van uitsluitings samenvoegen
- Nieuwe beheerinterfaces voor:
   - UDP-inspectie
   - Netwerkbeveiliging op Server 2019
   - IP-adresuitsluitingen voor netwerkbeveiliging
- Verbeterde zichtbaarheid van TPM-metingen
- Verbeterde Office VBA-module scannen

### <a name="known-issues"></a>Bekende problemen

Geen bekende problemen  
<br/>
</details>
<details>
<summary> Augustus-2020 (Platform: 4.18.2008.9 | Motor: 1.1.17400.5)</summary>

&ensp;Versie van beveiligingsinformatieupdate: **1.323.9.0**  
&ensp;Uitgebracht: **27 augustus 2020**  
&ensp;Platform: **4.18.2008.9**  
&ensp;Motor: **1.1.17400.5**  
&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**

### <a name="whats-new"></a>Wat is er nieuw

- Meer telemetriegebeurtenissen toevoegen
- Verbeterde telemetrie scangebeurtenis
- Verbeterde gedragscontrole voor geheugenscans
- Verbeterde macrostreams scannen
- Toegevoegd `AMRunningMode` aan Get-MpComputerStatus PowerShell-cmdlet
- [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wordt genegeerd. Microsoft Defender Antivirus wordt automatisch uitgeschakeld wanneer er een ander antivirusprogramma wordt gedetecteerd.


### <a name="known-issues"></a>Bekende problemen
Geen bekende problemen  
<br/>
</details>

<details>
<summary> Juli-2020 (Platform: 4.18.2007.8 | Motor: 1.1.17300.4)</summary>

&ensp;Versie van beveiligingsinformatieupdate: **1.321.30.0**  
&ensp;Uitgebracht: **28 juli 2020**  
&ensp;Platform: **4.18.2007.8**  
&ensp;Motor: **1.1.17300.4**  
&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**
    
### <a name="whats-new"></a>Wat is er nieuw

- Verbeterde telemetrie voor BITS
- Verbeterde validatie van Authenticode-code ondertekeningscertificaat

### <a name="known-issues"></a>Bekende problemen
Geen bekende problemen  
<br/>
</details>

<details>
<summary> Juni-2020 (Platform: 4.18.2006.10 | Motor: 1.1.17200.2)</summary>

&ensp;Versie van beveiligingsinformatieupdate: **1.319.20.0**  
&ensp;Uitgebracht: **22 juni 2020**  
&ensp;Platform: **4.18.2006.10**  
&ensp;Motor: **1.1.17200.2**  
&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**
    
### <a name="whats-new"></a>Wat is er nieuw

- Mogelijkheid om de locatie [van de ondersteuningslogboeken op te geven](./collect-diagnostic-data.md)
- Het overslaan van een agressieve inhaalscan in de passieve modus.
- Defender toestaan bij te werken op verbindingen met een datameter
- Vaste prestaties afstemmen wanneer caching is uitgeschakeld 
- Vaste registerquery 
- Randomisatie van scantime in ADMX opgelost

### <a name="known-issues"></a>Bekende problemen
Geen bekende problemen  
<br/>
</details>

<details>
<summary> Mei-2020 (Platform: 4.18.2005.4 | Motor: 1.1.17100.2)</summary>

&ensp;Versie van beveiligingsinformatieupdate: **1.317.20.0**  
&ensp;Uitgebracht: **26 mei 2020**  
&ensp;Platform: **4.18.2005.4**  
&ensp;Motor: **1.1.17100.2**  
&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**
    
### <a name="whats-new"></a>Wat is er nieuw

- Verbeterde logboekregistratie voor scangebeurtenissen
- Verbeterde crashafhandeling in de gebruikersmodus.
- Gebeurtenistracing toegevoegd voor Tamper-beveiliging
- AmSI-voorbeeldinzending opgelost
- AmSI Cloud blokkeren opgelost
- Installatielogboek voor beveiligingsupdates opgelost

### <a name="known-issues"></a>Bekende problemen
Geen bekende problemen  
<br/>
</details>

<details>
<summary> April-2020 (Platform: 4.18.2004.6 | Motor: 1.1.17000.2)</summary>

&ensp;Versie van beveiligingsinformatieupdate: **1.315.12.0**  
&ensp;Uitgebracht: **30 april 2020**  
&ensp;Platform: **4.18.2004.6**  
&ensp;Motor: **1.1.17000.2**  
&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**
    
### <a name="whats-new"></a>Wat is er nieuw
- Verbeteringen in WDfilter
- Meer actiebare gebeurtenisgegevens toevoegen om detectiegebeurtenissen voor surface reduction aan te vallen
- Vaste versiegegevens in diagnostische gegevens en WMI
- Onjuiste platformversie in gebruikersinterface na platformupdate opgelost
- Dynamic URL intel for Fileless threat protection
- UEFI-scanfunctie
- Logboekregistratie uitbreiden voor updates

### <a name="known-issues"></a>Bekende problemen
Geen bekende problemen  
<br/>
</details>

<details>
<summary> Maart-2020 (Platform: 4.18.2003.8 | Motor: 1.1.16900.2)</summary>

&ensp;Versie van beveiligingsinformatieupdate: **1.313.8.0**  
&ensp;Uitgebracht: **24 maart 2020**  
&ensp;Platform: **4.18.2003.8**  
&ensp;Motor: **1.1.16900.4**  
&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**
    
### <a name="whats-new"></a>Wat is er nieuw

- Optie CPU-beperking toegevoegd aan [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)
- Diagnostische mogelijkheden verbeteren
- time-out voor beveiligingsinformatie verminderen (5 min)
- Interne logfunctie voor AMSI-engine uitbreiden
- Melding voor procesblokkering verbeteren
   
### <a name="known-issues"></a>Bekende problemen
[**Opgelost**] Microsoft Defender Antivirus wordt bestanden overgeslagen tijdens het uitvoeren van een scan.

<br/>
</details>

<details>

<summary> Februari-2020 (Platform: - | Motor: 1.1.16800.2)</summary>
  

&ensp;Versie van beveiligingsinformatieupdate: **1.311.4.0**   
&ensp;Uitgebracht: **25 februari 2020**  
&ensp;Platform/client: **-**  
&ensp;Motor: **1.1.16800.2**  
&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**
     
### <a name="whats-new"></a>Wat is er nieuw

  
### <a name="known-issues"></a>Bekende problemen
Geen bekende problemen
<br/>
</details>

<details>
<summary> Januari-2020 (Platform: 4.18.2001.10 | Motor: 1.1.16700.2)</summary>
  

Versie van beveiligingsinformatieupdate: **1.309.32.0**  
Uitgebracht: **30 januari 2020**  
Platform/client: **4.18.2001.10**  
Motor: **1.1.16700.2**  
&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**
     
### <a name="whats-new"></a>Wat is er nieuw

- BSOD opgelost in WS2016 met Exchange
- Ondersteuningsplatformupdates wanneer TMP wordt omgeleid naar netwerkpad
- Platform- en engineversies worden toegevoegd aan [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) <!-- The preceding URL must include "/en-us" -->
- Update voor noodhandtekeningen uitbreiden [naar passieve modus](./microsoft-defender-antivirus-compatibility.md)
- Fix 4.18.1911.3 hang
   
### <a name="known-issues"></a>Bekende problemen

[**Opgelost**] apparaten die gebruikmaken van [de moderne stand-bymodus,](/windows-hardware/design/device-experiences/modern-standby) kunnen last hebben van de Windows Defender filtert stuurprogramma, wat resulteert in een gat in beveiliging.  Getroffen machines worden voor de klant weergegeven als niet bijgewerkt naar het nieuwste antimalwareplatform.  
<br/>
> [!IMPORTANT]
> Deze update is:
> - vereist door RS1-apparaten met een lagere versie van het platform ter ondersteuning van SHA2;
> - heeft een herstartvlag voor systemen met problemen met ophangen;
> - wordt opnieuw uitgebracht in april 2020 en wordt niet vervangen door nieuwere updates om toekomstige beschikbaarheid te behouden.  
> - wordt gecategoriseerd als een update vanwege de herstartvereiste; en
> - wordt alleen aangeboden met [Windows Update.](https://support.microsoft.com/help/4027667/windows-10-update)
<br/>
</details>

<details>
<summary> November-2019 (Platform: 4.18.1911.3 | Motor: 1.1.16600.7)</summary>

Versie van beveiligingsinformatieupdate: **1.307.13.0**  
Uitgebracht: **7 december 2019**  
Platform: **4.18.1911.3**  
Motor: **1.1.17000.7**  
Ondersteuningsfase: **Geen ondersteuning**  
     
### <a name="whats-new"></a>Wat is er nieuw

- MpCmdRun-traceringsniveau opgelost
- Versiegegevens van WDFilter opgelost
- Meldingen verbeteren (PUA)
- MRT-logboeken toevoegen om bestanden te ondersteunen
   
### <a name="known-issues"></a>Bekende problemen
Wanneer deze update is geïnstalleerd, moet het apparaat het jump-pakket 4.18.2001.10 gebruiken om te kunnen bijwerken naar de nieuwste platformversie.
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a>Microsoft Defender Antivirus platformondersteuning
Platform- en motorupdates worden geleverd op een maandelijkse cadans. Als u volledig wilt worden ondersteund, blijft u op de hoogte van de meest recente platformupdates. Onze ondersteuningsstructuur is dynamisch en verandert in twee fasen, afhankelijk van de beschikbaarheid van de nieuwste platformversie:

- **Servicefase beveiligings-** en kritieke updates: wanneer u de nieuwste platformversie gebruikt, komt u in aanmerking voor zowel beveiligings- als kritieke updates voor het anti-malwareplatform.
 
- **Technische ondersteuning (alleen) fase:** nadat een nieuwe platformversie is uitgebracht, wordt de ondersteuning voor oudere versies (N-2) beperkt tot alleen technische ondersteuning. Platformversies die ouder zijn dan N-2, worden niet meer ondersteund.*

\*Technische ondersteuning blijft beschikbaar voor upgrades van de Windows 10 releaseversie (zie Platformversie inbegrepen bij Windows 10 [releases)](#platform-version-included-with-windows-10-releases)naar de nieuwste platformversie.

Tijdens de fase van technische ondersteuning (alleen) worden commercieel redelijke ondersteuningsincidenten verstrekt via Microsoft Customer Service & Support en beheerde ondersteuningsaanbiedingen van Microsoft (zoals Premier Support). Als voor een ondersteuningsincident escalatie nodig is voor de ontwikkeling voor verdere richtlijnen, een niet-beveiligingsupdate vereist is of een beveiligingsupdate vereist, wordt klanten gevraagd een upgrade uit te voeren naar de nieuwste platformversie of een tussentijdse update (*).

### <a name="platform-version-included-with-windows-10-releases"></a>Platformversie inbegrepen bij Windows 10 releases
In de onderstaande tabel vindt u Microsoft Defender Antivirus platform- en engineversies die worden verzonden met de nieuwste Windows 10 releases:    

|Windows 10 release  |Platformversie  |Engine-versie |Ondersteuningsfase |
|:---|:---|:---|:---|
|2004 (20H1/20H2) |4.18.1909.6 |1.1.17000.2 | Ondersteuning voor technische upgrade (alleen) |
|1909 (19H2) |4.18.1902.5 |1.1.16700.3 | Ondersteuning voor technische upgrade (alleen) |
|1903 (19H1) |4.18.1902.5 |1.1.15600.4 | Ondersteuning voor technische upgrade (alleen) |
|1809 (RS5) |4.18.1807.18075 |1.1.15000.2 | Ondersteuning voor technische upgrade (alleen) |
|1803 (RS4) |4.13.17134.1 |1.1.14600.4 | Ondersteuning voor technische upgrade (alleen) |
|1709 (RS3) |4.12.16299.15 |1.1.14104.0 | Ondersteuning voor technische upgrade (alleen) |
|1703 (RS2) |4.11.15603.2 |1.1.13504.0 | Ondersteuning voor technische upgrade (alleen) |
|1607 (RS1) |4.10.14393.3683 |1.1.12805.0 | Ondersteuning voor technische upgrade (alleen) |  

Zie het Windows het Windows 10 voor meer informatie over [de release.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a>Updates voor implementatie van image Servicing and Management (DISM)

U wordt aangeraden uw Windows 10 (Enterprise-, Pro- en Home-edities), Windows Server 2019 en Windows Server 2016-installatieafbeeldingen van het besturingssysteem bij te werken met de nieuwste antivirus- en antimalware-updates. Als u de installatieafbeeldingen van uw besturingssysteem up-to-date houdt, voorkomt u een gat in beveiliging. 

Zie Microsoft Defender update voor Windows [installatieafbeeldingen](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)van het besturingssysteem voor meer informatie.

<details>
<summary>1.1.2106.01</summary>

&ensp;Pakketversie: **1.1.2106.01**    
&ensp;Platformversie: **4.18.2104.14**   
&ensp;Engine versie: **1.1.18100.6**  
&ensp;Handtekeningversie: **1.339.1923.0**    
    
### <a name="fixes"></a>Fixes
- Geen

### <a name="additional-information"></a>Aanvullende informatie
- Geen  
<br/>
</details><details>
<summary>1.1.2105.01</summary>

&ensp;Pakketversie: **1.1.2105.01**    
&ensp;Platformversie: **4.18.2103.7**   
&ensp;Engine versie: **1.1.18100.6**  
&ensp;Handtekeningversie: **1.339.42.0**    
    
### <a name="fixes"></a>Fixes
- Geen

### <a name="additional-information"></a>Aanvullende informatie
- Geen  
<br/>
</details><details>
<summary>1.1.2104.01</summary>

&ensp;Pakketversie: **1.1.2104.01**    
&ensp;Platformversie: **4.18.2102.4**   
&ensp;Engine-versie: **1.1.18000.5**  
&ensp;Handtekeningversie: **1.335.232.0**    
    
### <a name="fixes"></a>Fixes
- Geen

### <a name="additional-information"></a>Aanvullende informatie
- Geen  
<br/>
</details><details>
<summary>1.1.2103.01</summary>

&ensp;Pakketversie: **1.1.2103.01**    
&ensp;Platformversie: **4.18.2101.9**   
&ensp;Motorversie: **1.1.17800.5**  
&ensp;Handtekeningversie: **1.331.2302.0**    
    
### <a name="fixes"></a>Fixes
- Geen

### <a name="additional-information"></a>Aanvullende informatie
- Geen  
<br/>
</details><details>
<summary>1.1.2102.03</summary>

&ensp;Pakketversie: **1.1.2102.03**    
&ensp;Platformversie: **4.18.2011.6**   
&ensp;Motorversie: **1.1.17800.5**  
&ensp;Handtekeningversie: **1.331.174.0**    
    
### <a name="fixes"></a>Fixes
- Geen

### <a name="additional-information"></a>Aanvullende informatie
- Geen  
<br/>
</details><details>
<summary>1.1.2101.02</summary>

&ensp;Pakketversie: **1.1.2101.02**    
&ensp;Platformversie: **4.18.2011.6**   
&ensp;Motorversie: **1.1.17700.4**  
&ensp;Handtekeningversie: **1.329.1796.0**    
    
### <a name="fixes"></a>Fixes
- Geen

### <a name="additional-information"></a>Aanvullende informatie
- Geen  
<br/>
</details><details>
<summary>1.1.2012.01</summary>

&ensp;Pakketversie: **1.1.2012.01**    
&ensp;Platformversie: **4.18.2010.7**   
&ensp;Engine versie: **1.1.17600.5**  
&ensp;Handtekeningversie: **1.327.1991.0**    
    
### <a name="fixes"></a>Fixes
- Geen

### <a name="additional-information"></a>Aanvullende informatie
- Geen  
<br/>
</details><details>
<summary>1.1.2011.02</summary>

&ensp;Pakketversie: **1.1.2011.02**    
&ensp;Platformversie: **4.18.2010.7**   
&ensp;Engine versie: **1.1.17600.5**  
&ensp;Handtekeningversie: **1.327.658.0**    
    
### <a name="fixes"></a>Fixes
- Geen

### <a name="additional-information"></a>Aanvullende informatie
- Vernieuwde Microsoft Defender Antivirus handtekeningen  
<br/>
</details><details>
<summary>1.1.2011.01</summary>

&ensp;Pakketversie: **1.1.2011.01**    
&ensp;Platformversie: **4.18.2009.7**  
&ensp;Engine versie: **1.1.17600.5**  
&ensp;Handtekeningversie: **1.327.344.0**    
    
### <a name="fixes"></a>Fixes
- Geen

### <a name="additional-information"></a>Aanvullende informatie
- Geen  
<br/>
</details><details>
<summary>1.1.2009.10</summary>

&ensp;Pakketversie: **1.1.2011.01**    
&ensp;Platformversie: **4.18.2008.9**   
&ensp;Motorversie: **1.1.17400.5**  
&ensp;Handtekeningversie: **1.327.2216.0**    
    
### <a name="fixes"></a>Fixes
- Geen

### <a name="additional-information"></a>Aanvullende informatie
- Ondersteuning toegevoegd voor Windows 10 RS1- of hoger os-installatieafbeeldingen.  
<br/>
</details>

## <a name="additional-resources"></a>Aanvullende bronnen

| Artikel | Omschrijving  |
|:---|:---|
|[Microsoft Defender-update voor Windows installatieafbeeldingen van besturingssysteem](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | Controleer antimalware-updatepakketten voor installatieafbeeldingen van uw besturingssysteem (WIM- en VHD-bestanden). Ontvang Microsoft Defender Antivirus updates voor Windows 10 (Enterprise, Pro en Home editions), Windows Server 2019 en Windows Server 2016 installatieafbeeldingen.  |
|[Beheren hoe beveiligingsupdates worden gedownload en toegepast](manage-protection-updates-microsoft-defender-antivirus.md) | Beveiligingsupdates kunnen via veel bronnen worden geleverd. |
|[Beheren wanneer beveiligingsupdates moeten worden gedownload en toegepast](manage-protection-update-schedule-microsoft-defender-antivirus.md) | U kunt plannen wanneer beveiligingsupdates moeten worden gedownload. |
|[Updates beheren voor eindpunten die verouderd zijn](manage-outdated-endpoints-microsoft-defender-antivirus.md) | Als een eindpunt een update of geplande scan mist, kunt u een update forcen of scannen wanneer een gebruiker zich de volgende keer meldt. |
|[Op basis van gebeurtenissen afgedwongen updates beheren](manage-event-based-updates-microsoft-defender-antivirus.md) | U kunt instellen dat beveiligingsupdates worden gedownload bij het opstarten of na bepaalde beveiligingsgebeurtenissen in de cloud. |
|[Updates beheren voor mobiele apparaten en virtuele machines (VM's)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| U kunt instellingen opgeven, zoals of er updates moeten worden uitgevoerd op batterijvermogen, die vooral handig zijn voor mobiele apparaten en virtuele machines. |
