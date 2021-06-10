---
title: Regels voor de beperking van de surface-aanval gebruiken om malware-infectie te voorkomen
description: Met regels voor het verlagen van de surface-aanval kunt u voorkomen dat exploits apps en scripts gebruiken om apparaten met malware te infecteren.
keywords: Attack surface reduction rules, asr, hips, host intrusion prevention system, protection rules, anti-exploit, antiexploit, exploit, infection prevention, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f157a03d9a56aa0bbca695a27be57391e6b92360
ms.sourcegitcommit: 2cf7293d610a676726ac891b89366e23810d9142
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52866629"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a>Regels voor de beperking van de surface-aanval gebruiken om malware-infectie te voorkomen

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a>Waarom surface reduction-regels voor aanvallen belangrijk zijn

Het aanvalsoppervlak van uw organisatie bevat alle locaties waar een aanvaller de apparaten of netwerken van uw organisatie kan compromitteerden. Als u uw aanvalsoppervlak verkleint, moet u de apparaten en het netwerk van uw organisatie beschermen, waardoor aanvallers minder manieren hebben om aanvallen uit te voeren. Het configureren van regels voor het verlagen van de Surface-aanval in Microsoft Defender voor Eindpunt kan u helpen!

Attack surface reduction rules target certain software behaviors, such as:

- Uitvoerbare bestanden en scripts starten die proberen bestanden te downloaden of uit te voeren;
- Het uitvoeren van obfuscated of anderszins verdachte scripts; en
- Het uitvoeren van gedragingen die apps meestal niet starten tijdens normale dagelijkse werkzaamheden.

Dergelijke softwaregedragingen worden soms gezien in legitieme toepassingen. Deze gedragingen worden echter vaak als riskant beschouwd omdat ze vaak worden misbruikt door aanvallers via malware. Regels voor het beperken van het oppervlak van aanvallen kunnen riskant gedrag beperken en uw organisatie helpen beschermen.

Zie Voor meer informatie over het configureren van regels voor het configureren van de surface reduction-regels voor aanvallen De surface [reduction-regels inschakelen.](enable-attack-surface-reduction.md)

## <a name="assess-rule-impact-before-deployment"></a>Invloed van regel vóór implementatie beoordelen

U kunt beoordelen hoe een surface reduction-regel voor aanvallen van invloed kan zijn op uw netwerk door de beveiligingsaanbeveling voor die regel te openen in [Threat and Vulnerability Management.](/windows/security/threat-protection/#tvm)

:::image type="content" source="images/asrrecommendation.png" alt-text="Beveiligingsherinding voor de surface reduction-regel voor aanvallen":::

Controleer in het deelvenster aanbevelingsdetails of de invloed van de gebruiker is om te bepalen welk percentage van uw apparaten een nieuw beleid kan accepteren dat de regel in de blokkeringsmodus inschakelen zonder dat dit nadelig is voor de productiviteit.

## <a name="audit-mode-for-evaluation"></a>Controlemodus voor evaluatie

Gebruik [de auditmodus](audit-windows-defender.md) om te evalueren hoe de regels voor de beperking van de surface van de aanval van invloed zijn op uw organisatie als deze zijn ingeschakeld. Voer eerst alle regels uit in de auditmodus, zodat u kunt begrijpen hoe deze van invloed zijn op uw bedrijfstoepassingen. Veel line-of-business-toepassingen zijn geschreven met beperkte beveiligingsproblemen en ze kunnen taken uitvoeren op manieren die lijken op malware. Door controlegegevens te controleren en [uitsluitingen toe te](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) voegen voor benodigde toepassingen, kunt u regels voor de beperking van de surface-aanval implementeren zonder de productiviteit te verlagen.

## <a name="warn-mode-for-users"></a>Waarschuwingsmodus voor gebruikers

(**NIEUW**!) Voordat u de modusfuncties waarschuwt, kunnen regels voor het verlagen van de surface die zijn ingeschakeld, worden ingesteld op de auditmodus of de blokmodus. Met de nieuwe waarschuwingsmodus zien gebruikers een dialoogvenster waarin wordt aangegeven dat de inhoud is geblokkeerd wanneer inhoud wordt geblokkeerd door een regel voor het verlagen van het aanvalsoppervlak. Het dialoogvenster biedt de gebruiker ook de optie om de blokkering van de inhoud te deblokkeren. De gebruiker kan vervolgens zijn of haar actie opnieuw uitvoeren en de bewerking wordt voltooid. Wanneer een gebruiker inhoud deblokkert, blijft de inhoud 24 uur lang geblokkeerd en worden cv's geblokkeerd.

Met de waarschuwingsmodus kan uw organisatie regels voor de beperking van de surface hebben, zonder dat gebruikers toegang hebben tot de inhoud die ze nodig hebben om hun taken uit te voeren.

### <a name="requirements-for-warn-mode-to-work"></a>Vereisten voor de waarschuwingsmodus om te werken

De waarschuwingsmodus wordt ondersteund op apparaten met de volgende versies van Windows:

- [Windows 10, versie 1809](/windows/whats-new/whats-new-windows-10-version-1809) of hoger
- [Windows Server, versie 1809](/windows-server/get-started/whats-new-in-windows-server-1809) of hoger

Microsoft Defender Antivirus moet worden uitgevoerd met realtime beveiliging in [de actieve modus.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)

Zorg er bovendien voor dat [Microsoft Defender Antivirus en antimalware-updates](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) zijn geïnstalleerd.

- Minimale vereiste voor het vrijgeven van platformen: `4.18.2008.9`
- Minimale vereiste voor het vrijgeven van de motor: `1.1.17400.5`

Zie Update for Microsoft Defender [antimalware platform (Update voor Microsoft Defender antimalwareplatform)](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)voor meer informatie en om uw updates te downloaden.

### <a name="cases-where-warn-mode-is-not-supported"></a>Gevallen waarin de waarschuwingsmodus niet wordt ondersteund

De waarschuwingsmodus wordt niet ondersteund voor drie regels voor het verlagen van het aanvalsoppervlak wanneer u deze configureert in Microsoft Endpoint Manager. (Als u groepsbeleid gebruikt om de regels voor het verlagen van de aanvalsoppervlakken te configureren, wordt de waarschuwingsmodus ondersteund.) De drie regels die de waarschuwingsmodus niet ondersteunen wanneer u deze configureert in Microsoft Endpoint Manager zijn als volgt:

- [JavaScript of VBScript blokkeren om gedownloade uitvoerbare inhoud](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID) te starten `d3e037e1-3eb8-44c8-a917-57927947596d`
- [Persistentie blokkeren via WMI-gebeurtenisabonnement](#block-persistence-through-wmi-event-subscription) `e6db77e5-3df2-4cf1-b95a-636979351e5b` (GUID)
- [Geavanceerde beveiliging tegen ransomware](#use-advanced-protection-against-ransomware) (GUID) `c1db55ab-c21a-4637-bb3f-a12568109d35` gebruiken

Bovendien wordt de waarschuwingsmodus niet ondersteund op apparaten met oudere versies van Windows. In dat geval worden de regels voor de beperking van het oppervlak die zijn geconfigureerd voor het uitvoeren van de waarschuwingsmodus uitgevoerd in de blokmodus uitgevoerd.

## <a name="notifications-and-alerts"></a>Meldingen en waarschuwingen

Wanneer een surface reduction-regel voor aanvallen wordt geactiveerd, wordt er een melding weergegeven op het apparaat. U kunt [de melding aanpassen met](customize-attack-surface-reduction.md#customize-the-notification) uw bedrijfsgegevens en contactgegevens.

Bovendien worden waarschuwingen gegenereerd wanneer bepaalde regels voor de beperking van het aanvalsoppervlak worden geactiveerd.

Meldingen en eventuele waarschuwingen die worden gegenereerd, kunnen worden bekeken in het Microsoft Defender-beveiligingscentrum ( ) en [https://securitycenter.windows.com](https://securitycenter.windows.com) in het Microsoft 365 beveiligingscentrum ( [https://security.microsoft.com](https://security.microsoft.com) ).

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a>Geavanceerde gebeurtenissen bij het zoeken en aanvallen van oppervlakten

U kunt geavanceerde jacht gebruiken om gebeurtenissen met een aanvalsoppervlak te bekijken. Als u het volume van binnenkomende gegevens wilt stroomlijnen, kunnen alleen unieke processen voor elk uur worden bekeken met geavanceerde jacht. De tijd van een aanvalsoppervlakverkortingsgebeurtenis is de eerste keer dat de gebeurtenis binnen het uur wordt gezien.

Stel dat een surface reduction-gebeurtenis voor aanvallen plaatsvindt op 10 apparaten tijdens de 14:00 uur. Stel dat de eerste gebeurtenis plaatsvond om 2:15 en de laatste om 2:45. Met geavanceerd zoeken ziet u één exemplaar van die gebeurtenis (ook al heeft deze zich daadwerkelijk op tien apparaten voorgedaan) en de tijdstempel is 14:15 uur.

Zie Proactief zoeken naar bedreigingen met geavanceerde jacht voor meer informatie over geavanceerde [jacht.](advanced-hunting-overview.md)

## <a name="attack-surface-reduction-features-across-windows-versions"></a>Surface Reduction-functies voor aanvallen in Windows versies

U kunt regels voor de beperking van de surface voor aanvallen instellen voor apparaten met een van de volgende versies en versies van Windows:

- Windows 10 Pro, versie [1709](/windows/whats-new/whats-new-windows-10-version-1709) of hoger
- Windows 10 Enterprise, versie [1709](/windows/whats-new/whats-new-windows-10-version-1709) of hoger
- Windows Server, [versie 1803 (halfjaarlijks kanaal)](/windows-server/get-started/whats-new-in-windows-server-1803) of hoger
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Hoewel voor de regels voor het verminderen van aanvallen geen [E5-licentie](/windows/deployment/deploy-enterprise-licenses)Windows vereist, krijgt u geavanceerde beheermogelijkheden als u Windows E5 hebt. Deze mogelijkheden zijn alleen beschikbaar in Windows E5, zoals monitoring, analyse en werkstromen die beschikbaar zijn in [Defender voor](microsoft-defender-endpoint.md)Eindpunt, evenals rapportage- en configuratiemogelijkheden in het [Microsoft 365 beveiligingscentrum.](/microsoft-365/security/defender/overview-security-center) Deze geavanceerde mogelijkheden zijn niet beschikbaar met een Windows Professional- of Windows E3-licentie. Als u echter wel over deze licenties hebt, kunt u Gebeurtenisviewer en logboeken Microsoft Defender Antivirus om de gebeurtenissen in de surface reduction rule van uw aanval te bekijken.

## <a name="review-attack-surface-reduction-events-in-the-microsoft-defender-security-center"></a>Gebeurtenissen in de surface reduction van de aanval in de Microsoft Defender-beveiligingscentrum

Defender voor Eindpunt biedt gedetailleerde rapportage voor gebeurtenissen en blokken als onderdeel van scenario's voor waarschuwingsonderzoek.

U kunt Defender voor eindpuntgegevens query's uitvoeren met [behulp van geavanceerd zoeken.](advanced-hunting-query-language.md) Als u de auditmodus [gebruikt,](audit-windows-defender.md)kunt u geavanceerde zoekwerkzaamheden gebruiken om te begrijpen hoe de regels voor het beperken van het oppervlak van de aanval van invloed kunnen zijn op uw omgeving.

Hier is een voorbeeldquery:

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Gebeurtenissen voor het verminderen van aanvallen in Windows eventviewer bekijken

U kunt het logboek met Windows bekijken om gebeurtenissen weer te geven die zijn gegenereerd door regels voor het verminderen van het oppervlak van de aanval:

1. Download het [evaluatiepakket en](https://aka.ms/mp7z2w) haal het *bestand* cfa-events.xmlnaar een gemakkelijk toegankelijke locatie op het apparaat.
2. Voer de woorden, *Gebeurtenisviewer,* in het menu Start in om de Windows Gebeurtenisviewer te openen.
3. Selecteer **onder Acties** de optie Aangepaste weergave **importeren...**.
4. Selecteer de *bestandsindelingcfa-events.xml* waar het is geëxtraheerd. U kunt ook [de XML rechtstreeks kopiëren.](event-views.md)
5. Selecteer **OK**.

U kunt een aangepaste weergave maken waarmee gebeurtenissen worden gefilterd om alleen de volgende gebeurtenissen weer te geven, die allemaal betrekking hebben op gecontroleerde maptoegang:

|Gebeurtenis-id|Omschrijving|
|---|---|
|5007|Gebeurtenis wanneer instellingen worden gewijzigd|
|1121|Gebeurtenis wanneer regel wordt branden in de blokmodus|
|1122|Gebeurtenis wanneer regel wordt branden in de auditmodus|

De 'engine-versie' die wordt vermeld voor gebeurtenissen met een beperking van het aanvalsoppervlak in het gebeurtenislogboek, wordt gegenereerd door Defender voor Eindpunt, niet door het besturingssysteem. Defender voor Eindpunt is geïntegreerd met Windows 10, dus deze functie werkt op alle apparaten met Windows 10 geïnstalleerd.

## <a name="attack-surface-reduction-rules"></a>Regels voor het verminderen van kwetsbaarheid voor aanvallen

In de volgende tabel en subsecties worden elk van de 15 regels voor het verminderen van het oppervlak beschreven. De regels voor de beperking van de aanvalsoppervlakken worden op naam van de regel in alfabetische volgorde weergegeven.

Als u de regels voor het verlagen van de aanvalsoppervlakken configureert met groepsbeleid of PowerShell, hebt u de GUID's nodig. Als u echter een Microsoft Endpoint Manager of Microsoft Intune gebruikt, hebt u de GUID's niet nodig.

|Regelnaam|GUID|Bestand & mapuitsluitingen|Minimaal ondersteund besturingssysteem|
|---|:---:|---|---|
|[Misbruik van uitgebuite, kwetsbare ondertekende stuurprogramma's blokkeren](#block-abuse-of-exploited-vulnerable-signed-drivers)|`56a863a9-875e-4185-98a7-b882c64b5ce5`|Ondersteund|[Windows 10, versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) of hoger) |
|[Adobe Reader blokkeren om onderliggende processen te maken](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|Ondersteund|[Windows 10 versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) of hoger|
|[Alle toepassingen Office voor het maken van onderliggende processen blokkeren](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|Ondersteund|[Windows 10 versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) of hoger|
|[Referenties van het subsysteem van de Windows lokale beveiligingsinstantie blokkeren (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|Ondersteund|[Windows 10 versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) of hoger|
|[Uitvoerbare inhoud van e-mailclient en webmail blokkeren](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|Ondersteund|[Windows 10 versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) of hoger|
|[Het uitvoeren van uitvoerbare bestanden blokkeren, tenzij ze voldoen aan een criterium voor gebruik, leeftijd of vertrouwde lijst](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|Ondersteund|[Windows 10 versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) of hoger|
|[De uitvoering van mogelijk obfuscated scripts blokkeren](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|Ondersteund|[Windows 10 versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) of hoger|
|[JavaScript of VBScript blokkeren om gedownloade uitvoerbare inhoud te starten](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|Ondersteund|[Windows 10 versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) of hoger|
|[Voorkomen Office het maken van uitvoerbare inhoud](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|Ondersteund|[Windows 10 versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) of hoger|
|[Het Office blokkeren om code in andere processen te injecteren](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|Ondersteund|[Windows 10 versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) of hoger|
|[Blokkeren Office communicatietoepassing om onderliggende processen te maken](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|Ondersteund|[Windows 10 versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) of hoger|
|[Persistentie blokkeren via WMI-gebeurtenisabonnement](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|Niet ondersteund|[Windows 10 versie 1903](/windows/whats-new/whats-new-windows-10-version-1903) (build 18362) of hoger|
|[Procescreaties blokkeren die afkomstig zijn van PSExec- en WMI-opdrachten](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|Ondersteund|[Windows 10 versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) of hoger|
|[Niet-vertrouwde en niet-ondertekende processen blokkeren die worden uitgevoerd via USB](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|Ondersteund|[Windows 10 versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) of hoger|
|[Win32 API-oproepen blokkeren Office macro's](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|Ondersteund|[Windows 10 versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) of hoger|
|[Geavanceerde beveiliging tegen ransomware gebruiken](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|Ondersteund|[Windows 10 versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) of hoger|
|

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a>Misbruik van uitgebuite, kwetsbare ondertekende stuurprogramma's blokkeren

Met deze regel voorkomt u dat een toepassing een kwetsbaar, ondertekend stuurprogramma naar schijf schrijft. In-the-wild, kwetsbaar ondertekende stuurprogramma's kunnen worden gebruikt door lokale toepassingen die voldoende bevoegdheden hebben om toegang te \-  \- krijgen tot de kernel. Met kwetsbaar ondertekende stuurprogramma's kunnen aanvallers beveiligingsoplossingen uitschakelen of omzeilen, wat uiteindelijk leidt tot systeemcompromitteerdheid.

Met deze regel wordt niet geblokkeerd dat een stuurprogramma dat al in het systeem bestaat, wordt geladen.

>[!NOTE]
>
> Deze regel kan worden geconfigureerd met [mem oma-URI](enable-attack-surface-reduction.md#mem) voor proceduregegevens voor aangepaste regels voor MEM OMA-URI.
>
> Deze regel kan ook worden geconfigureerd met [PowerShell.](enable-attack-surface-reduction.md#powershell)
>
> U kunt deze website gebruiken om een stuurprogramma [voor analyse in te dienen.](https://www.microsoft.com/en-us/wdsi/driversubmission)

Deze regel wordt ondersteund in alle versies waarin ASR wordt ondersteund. dat wil zeggen:

- [Windows 10 Pro, versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) of hoger
- [Windows 10 Enterprise, versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) of hoger
- [Windows Server, versie 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) of hoger
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Intune-naam: `Block abuse of exploited vulnerable signed drivers`

GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`

### <a name="block-adobe-reader-from-creating-child-processes"></a>Adobe Reader blokkeren om onderliggende processen te maken

Met deze regel voorkomt u aanvallen door te blokkeren dat Adobe Reader processen maakt.

Via social engineering of exploits kan malware payloads downloaden en starten en uit Adobe Reader breken. Door te voorkomen dat onderliggende processen worden gegenereerd door Adobe Reader, kan malware die deze als vector probeert te gebruiken, niet worden verspreid.

Deze regel is geïntroduceerd in:

- [Windows 10, versie 1809](/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Server, versie 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Intune-naam: `Process creation from Adobe Reader (beta)`

Naam van Configuration Manager: Nog niet beschikbaar

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

### <a name="block-all-office-applications-from-creating-child-processes"></a>Alle toepassingen Office voor het maken van onderliggende processen blokkeren

Met deze regel Office apps geen onderliggende processen maken. Office apps zijn Word, Excel, PowerPoint, OneNote en Access.

Het maken van schadelijke onderliggende processen is een veelgebruikte malwarestrategie. Malware die misbruik Office als vector, bevat vaak VBA-macro's en gebruikt code om meer payloads te downloaden en uit te voeren. Sommige legitieme line-of-business-toepassingen kunnen echter ook onderliggende processen genereren voor goedaardige doeleinden, zoals het genereren van een opdrachtprompt of het gebruik van PowerShell om registerinstellingen te configureren.

Deze regel is geïntroduceerd in:

- [Windows 10, versie 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versie 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune-naam: `Office apps launching child processes`

Naam van Configuration Manager: `Block Office application from creating child processes`

GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>Referenties van het subsysteem van de Windows lokale beveiligingsinstantie blokkeren

Met deze regel voorkomt u het stelen van referenties door LSASS (Local Security Authority Subsystem Service) te vergrendelen.

LSASS verifieert gebruikers die zich aanmelden op een Windows computer. Microsoft Defender Credential Guard in Windows 10 voorkomt gewoonlijk pogingen om referenties op te halen uit LSASS. Sommige organisaties kunnen Credential Guard echter niet op al hun computers inschakelen vanwege compatibiliteitsproblemen met aangepaste smartcard-stuurprogramma's of andere programma's die worden geladen in de LSA (Local Security Authority). In deze gevallen kunnen aanvallers hackhulpmiddelen zoals Mimikatz gebruiken om cleartext-wachtwoorden en NTLM-hashes van LSASS te schrapen.

> [!NOTE]
> In sommige apps worden alle lopende processen in de code op een lijst met volledige machtigingen geopend. Met deze regel wordt de actie voor het openen van het proces van de app ontnomen en worden de details bij het logboek met beveiligingsgebeurtenissen bij de logboeken van de beveiligingsgebeurtenissen bij de app bij de logboeken van de beveiligingsgebeurtenissen. Deze regel kan veel ruis genereren. Als u een app hebt die alleen LSASS opsnoemt, maar geen echte invloed heeft op functionaliteit, hoeft u deze niet toe te voegen aan de uitsluitingslijst. Deze gebeurtenislogboekinvoer geeft op zichzelf niet per se een schadelijke bedreiging aan.

Deze regel is geïntroduceerd in:

- [Windows 10, versie 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, versie 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Intune-naam: `Flag credential stealing from the Windows local security authority subsystem`

Naam van Configuration Manager: `Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

### <a name="block-executable-content-from-email-client-and-webmail"></a>Uitvoerbare inhoud van e-mailclient en webmail blokkeren

Deze regel blokkeert dat de volgende bestandstypen worden geopend vanuit e-mail die is geopend in de Microsoft Outlook-toepassing, of Outlook.com en andere populaire webmailproviders:

- Uitvoerbare bestanden (zoals .exe, .dll of .scr)
- Scriptbestanden (zoals een PowerShell .ps, Visual Basic .vbs of JavaScript-.js bestand)

Deze regel is geïntroduceerd in:

- [Windows 10, versie 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versie 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Microsoft Endpoint Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune-naam: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft Endpoint Manager naam:`Block executable content from email client and webmail`

GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`

> [!NOTE]
> De regel **Uitvoerbare inhoud van e-mailclient** en webmail blokkeren heeft de volgende alternatieve beschrijvingen, afhankelijk van welke toepassing u gebruikt:
>
> - Intune (configuratieprofielen): Uitvoering van uitvoerbare inhoud (exe, dll, ps, js, vbs, enzovoort) die is weggelaten uit e-mail (webmail/e-mailclient) (geen uitzonderingen).
> - Endpoint Manager: downloadbare inhoud van e-mail- en webmail-clients blokkeren.
> - Groepsbeleid: Uitvoerbare inhoud van e-mailclient en webmail blokkeren.

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>Het uitvoeren van uitvoerbare bestanden blokkeren, tenzij ze voldoen aan een criterium voor gebruik, leeftijd of vertrouwde lijst

Deze regel blokkeert het starten van de volgende bestandstypen, tenzij ze voldoen aan de prevalentie- of leeftijdscriteria, of als ze in een vertrouwde lijst of een uitsluitingslijst staan:

- Uitvoerbare bestanden (zoals .exe, .dll of .scr)

Het starten van niet-vertrouwde of onbekende uitvoerbare bestanden kan riskant zijn, omdat het in eerste instantie niet duidelijk is of de bestanden schadelijk zijn.

> [!IMPORTANT]
> U moet [beveiliging in de cloud inschakelen](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) om deze regel te kunnen gebruiken.
>
> De regel **Voorkomen dat uitvoerbare** bestanden worden uitgevoerd, tenzij ze voldoen aan een criterium voor gebruik, leeftijd of vertrouwde lijst met GUID, is eigendom van Microsoft en wordt niet opgegeven `01443614-cd74-433a-b99e-2ecdc07bfc25` door beheerders. Met deze regel wordt beveiliging in de cloud gebruikt om de vertrouwde lijst regelmatig bij te werken.
>
> U kunt afzonderlijke bestanden of mappen opgeven (met behulp van mappaden of volledig gekwalificeerde resourcenamen), maar u kunt niet opgeven op welke regels of uitsluitingen van toepassing zijn.

Deze regel is geïntroduceerd in:

- [Windows 10, versie 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, versie 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Intune-naam: `Executables that don't meet a prevalence, age, or trusted list criteria`

Naam van Configuration Manager: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>De uitvoering van mogelijk obfuscated scripts blokkeren

Met deze regel worden verdachte eigenschappen gedetecteerd in een obfuscated script.

Script obfuscation is een veelgebruikte techniek die zowel malwareauteurs als legitieme toepassingen gebruiken om intellectuele eigendom te verbergen of de laadtijden van scripts te verminderen. Malwareauteurs gebruiken ook obfuscation om schadelijke code moeilijker te lezen te maken, waardoor mensen en beveiligingssoftware niet nauwkeurig worden gecontroleerd.

Deze regel is geïntroduceerd in:

- [Windows 10, versie 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versie 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune-naam: `Obfuscated js/vbs/ps/macro code`

Naam van Configuration Manager: `Block execution of potentially obfuscated scripts`

GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>JavaScript of VBScript blokkeren om gedownloade uitvoerbare inhoud te starten

Met deze regel voorkomt u dat scripts potentieel schadelijke gedownloade inhoud starten. Malware die is geschreven in JavaScript of VBScript fungeert vaak als downloader om andere malware van internet op te halen en te starten.

Hoewel dit niet gebruikelijk is, worden in line-of-business-toepassingen soms scripts gebruikt om installatieprogramma's te downloaden en te starten.

Deze regel is geïntroduceerd in:

- [Windows 10, versie 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versie 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune-naam: `js/vbs executing payload downloaded from Internet (no exceptions)`

Naam van Configuration Manager: `Block JavaScript or VBScript from launching downloaded executable content`

GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`

### <a name="block-office-applications-from-creating-executable-content"></a>Voorkomen Office het maken van uitvoerbare inhoud

Deze regel voorkomt dat Office apps, waaronder Word, Excel en PowerPoint, potentieel schadelijke uitvoerbare inhoud kunnen maken door te voorkomen dat schadelijke code op schijf wordt geschreven.

Malware die misbruik maakt van Office vector kan proberen uit te breken Office schadelijke onderdelen op schijf op te slaan. Deze schadelijke onderdelen overleven een computer opnieuw opstarten en blijven op het systeem staan. Daarom wordt met deze regel een veelvoorkomende persistentietechniek gebruikt.

Deze regel is geïntroduceerd in:

- [Windows 10, versie 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versie 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [System Center Configuration Manager](/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM is nu Microsoft Endpoint Configuration Manager)

Intune-naam: `Office apps/macros creating executable content`

SCCM-naam: `Block Office applications from creating executable content`

GUID: `3B576869-A4EC-4529-8536-B80A7769E899`

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>Het Office blokkeren om code in andere processen te injecteren

Met deze regel worden pogingen tot codeinjectie Office apps in andere processen.

Aanvallers kunnen proberen om via Office kwaadaardige code te migreren naar andere processen via code-injectie, zodat de code zich kan voordoen als een schoon proces.

Er zijn geen bekende legitieme zakelijke doeleinden voor het gebruik van code-injectie.

Deze regel is van toepassing op Word, Excel en PowerPoint.

Deze regel is geïntroduceerd in:

- [Windows 10, versie 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versie 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune-naam: `Office apps injecting code into other processes (no exceptions)`

Naam van Configuration Manager: `Block Office applications from injecting code into other processes`

GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`

### <a name="block-office-communication-application-from-creating-child-processes"></a>Blokkeren Office communicatietoepassing om onderliggende processen te maken

Deze regel voorkomt dat Outlook onderliggende processen maakt, terwijl er nog steeds legitieme Outlook functies.

Deze regel beschermt tegen social engineering-aanvallen en voorkomt dat misbruik van code misbruik maakt van beveiligingslekken in Outlook. Het beschermt ook tegen Outlook regels en formulieren [die aanvallers](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) kunnen gebruiken wanneer de referenties van een gebruiker worden gehackt.

> [!NOTE]
> Deze regel blokkeert DLP-beleidstips en ToolTips in Outlook. Deze regel is alleen van Outlook en Outlook.com. 

Deze regel is geïntroduceerd in:

- [Windows 10, versie 1809](/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Server, versie 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Intune-naam: `Process creation from Office communication products (beta)`

Naam van Configuration Manager: Niet beschikbaar

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

### <a name="block-persistence-through-wmi-event-subscription"></a>Persistentie blokkeren via WMI-gebeurtenisabonnement

Met deze regel voorkomt u dat malware misbruik maakt van WMI om persistentie te bereiken op een apparaat.

> [!IMPORTANT]
> Bestands- en mapuitsluitingen zijn niet van toepassing op deze regel voor het verminderen van het oppervlak van de aanval.

Bestandsloze bedreigingen gebruiken verschillende tactieken om verborgen te blijven, om te voorkomen dat ze worden gezien in het bestandssysteem en om periodieke uitvoeringscontrole te krijgen. Sommige bedreigingen kunnen misbruik maken van de WMI-opslagplaats en het gebeurtenismodel om verborgen te blijven.

Deze regel is geïntroduceerd in:

- [Windows 10, versie 1903](/windows/whats-new/whats-new-windows-10-version-1903)
- [Windows Server 1903](/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

Intune-naam: Niet beschikbaar

Naam van Configuration Manager: Niet beschikbaar

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>Procescreaties blokkeren die afkomstig zijn van PSExec- en WMI-opdrachten

Met deze regel worden processen die zijn gemaakt [via PsExec](/sysinternals/downloads/psexec) en [WMI,](/windows/win32/wmisdk/about-wmi) niet uitgevoerd. Zowel PsExec als WMI kunnen code op afstand uitvoeren, dus bestaat het risico dat deze functionaliteit wordt misbruikt voor opdracht- en beheerdoeleinden of om een infectie over het netwerk van een organisatie te verspreiden.

> [!WARNING]
> Gebruik deze regel alleen als u uw apparaten beheert met [Intune](/intune) of een andere MDM-oplossing. Deze regel is niet compatibel met beheer [via Microsoft Endpoint Configuration Manager](/configmgr) omdat deze regel WMI-opdrachten blokkeert die de Configuration Manager-client gebruikt om correct te werken.

Deze regel is geïntroduceerd in:

- [Windows 10, versie 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, versie 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Intune-naam: `Process creation from PSExec and WMI commands`

Naam van Configuration Manager: Niet van toepassing

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>Niet-vertrouwde en niet-ondertekende processen blokkeren die worden uitgevoerd via USB

Met deze regel kunnen beheerders voorkomen dat niet-ondertekende of niet-vertrouwde uitvoerbare bestanden worden uitgevoerd via verwisselbare USB-stations, waaronder SD-kaarten. Geblokkeerde bestandstypen bevatten uitvoerbare bestanden (zoals .exe, .dll of .scr)

Deze regel is geïntroduceerd in:

- [Windows 10, versie 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, versie 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Intune-naam: `Untrusted and unsigned processes that run from USB`

Naam van Configuration Manager: `Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

### <a name="block-win32-api-calls-from-office-macros"></a>Win32 API-oproepen blokkeren Office macro's

Met deze regel voorkomt u dat VBA-macro's Win32-API's bellen.

Office VBA schakelt Win32 API-oproepen in. Malware kan misbruik maken van deze mogelijkheid, zoals het bellen van [Win32-API's](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) om schadelijke shellcode te starten zonder iets rechtstreeks op de schijf te schrijven. De meeste organisaties vertrouwen niet op de mogelijkheid om Win32-API's te bellen in hun dagelijkse werking, zelfs niet als ze macro's op andere manieren gebruiken.

Deze regel is geïntroduceerd in:

- [Windows 10, versie 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versie 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune-naam: `Win32 imports from Office macro code`

Naam van Configuration Manager: `Block Win32 API calls from Office macros`

GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`

### <a name="use-advanced-protection-against-ransomware"></a>Geavanceerde beveiliging tegen ransomware gebruiken

Deze regel biedt een extra beschermingslaag tegen ransomware. Er worden zowel client- als cloud-heuristische gegevens gebruikt om te bepalen of een bestand op ransomware lijkt. Met deze regel worden bestanden met een of meer van de volgende kenmerken niet geblokkeerd:

- Het bestand is al ongeschonden in de Microsoft-cloud gevonden.
- Het bestand is een geldig ondertekend bestand.
- Het bestand is overwegend genoeg om niet als ransomware te worden beschouwd.

De regel heeft de neiging om voorzichtig te zijn om ransomware te voorkomen.

> [!NOTE]
> U moet [beveiliging in de cloud inschakelen](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) om deze regel te kunnen gebruiken.

Deze regel is geïntroduceerd in:

- [Windows 10, versie 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, versie 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Intune-naam: `Advanced ransomware protection`

Naam van Configuration Manager: `Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`

## <a name="see-also"></a>Zie ook

- [Veelgestelde vragen over het verminderen van kwetsbaarheid voor aanvallen](attack-surface-reduction-faq.md)
- [Regels voor het verminderen van aanvalsoppervlakken inschakelen](enable-attack-surface-reduction.md)
- [Regels voor het verminderen van kwetsbaarheid voor aanvallen evalueren](evaluate-attack-surface-reduction.md)
- [Compatibiliteit van Microsoft Defender Antivirus met andere antivirus-/antimalwareoplossingen](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
