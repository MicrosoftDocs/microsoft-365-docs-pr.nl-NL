---
title: Surface Reduction-regels voor aanvallen aanpassen
description: Stel afzonderlijk regels in audit-, blok- of uitgeschakelde modi in en voeg bestanden en mappen toe die moeten worden uitgesloten van de regels voor de beperking van het aanvalsoppervlak
keywords: Aanvalsoppervlakverminding, hips, host intrusion prevention system, protection rules, anti-exploit, anti-exploit, exploit, infection prevention, customize, configure, exclude
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 99a88a869c8a79f79cbc3a16fc73bf556416c51a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163292"
---
# <a name="customize-attack-surface-reduction-rules"></a>Surface Reduction-regels voor aanvallen aanpassen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.

[Met surface reduction-regels voor aanvallen](enable-attack-surface-reduction.md) kunt u voorkomen dat softwaregedrag vaak wordt misbruikt om uw apparaat of netwerk in gevaar te brengen. Een aanvaller kan bijvoorbeeld proberen een niet-ondertekend script uit te voeren op een USB-station of een macro in een Office-document rechtstreeks laten bellen naar de Win32-API. Regels voor het beperken van het oppervlak van aanvallen kunnen dit soort riskante gedragingen beperken en de defensieve houding van uw organisatie verbeteren.

Lees hoe u regels voor [](#exclude-files-and-folders) het verminderen van [](#customize-the-notification) aanvallen kunt aanpassen door bestanden en mappen uit te sluiten of aangepaste tekst toe te voegen aan de meldingsmelding die op de computer van een gebruiker wordt weergegeven.

U kunt regels voor de beperking van de surface voor aanvallen instellen voor apparaten met een van de volgende versies en versies van Windows:
- Windows 10 Pro, [versie 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) of hoger
- Windows 10 Enterprise, [versie 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) of hoger
- Windows Server, [versie 1803 (halfjaarlijks kanaal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) of hoger
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19) U kunt group policy, PowerShell en Mobile Device Management (MDM) configuration service providers (CSP) gebruiken om deze instellingen te configureren.

## <a name="exclude-files-and-folders"></a>Bestanden en mappen uitsluiten

U kunt ervoor kiezen om uit te sluiten dat bestanden en mappen worden geëvalueerd door regels voor het verminderen van het oppervlak van de aanval. Wanneer het bestand is uitgesloten, wordt het niet geblokkeerd, zelfs niet als een surface reduction-regel voor aanvallen detecteert dat het bestand schadelijk gedrag bevat.

> [!WARNING]
> Hierdoor kunnen onveilige bestanden mogelijk worden uitgevoerd en uw apparaten kunnen worden geïnfecteerd. Het uitsluiten van bestanden of mappen kan de beveiliging die wordt geboden door regels voor het beperken van het oppervlak van de aanval, aanzienlijk beperken. Bestanden die door een regel zijn geblokkeerd, kunnen worden uitgevoerd en er wordt geen rapport of gebeurtenis opgenomen.

Een uitsluiting is van toepassing op alle regels die uitsluitingen toestaan. U kunt een afzonderlijk bestand, mappad of de volledig gekwalificeerde domeinnaam voor een resource opgeven. U kunt een uitsluiting echter niet beperken tot een specifieke regel.

Een uitsluiting wordt alleen toegepast wanneer de uitgesloten toepassing of service wordt gestart. Als u bijvoorbeeld een uitsluiting toevoegt voor een updateservice die al wordt uitgevoerd, blijft de updateservice gebeurtenissen activeren totdat de service is gestopt en opnieuw wordt gestart.

Attack Surface Reduction ondersteunt omgevingsvariabelen en jokertekens. Zie Jokertekens gebruiken in de lijsten met bestandsnaam en mappaden of [uitbreidingsuitsluitingen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)voor informatie over het gebruik van jokertekens.
Als u problemen ondervindt met regels voor het detecteren van bestanden die volgens u niet moeten worden gedetecteerd, gebruikt u de auditmodus om [de regel te testen.](evaluate-attack-surface-reduction.md)

Beschrijving van regel | GUID
-|-|-
Alle Office-toepassingen blokkeren om onderliggende processen te maken | D4F940AB-401B-4EFC-AADC-AD5F3C50688A
De uitvoering van mogelijk obfuscated scripts blokkeren | 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC
Win32 API-oproepen blokkeren vanuit Office-macro | 92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B
Voorkomen dat Office-toepassingen uitvoerbare inhoud maken | 3B576869-A4EC-4529-8536-B80A7769E899
Office-toepassingen blokkeren om code in andere processen te injecteren | 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84
JavaScript of VBScript blokkeren om gedownloade uitvoerbare inhoud te starten | D3E037E1-3EB8-44C8-A917-57927947596D
Uitvoerbare inhoud van e-mailclient en webmail blokkeren | BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550
Het uitvoeren van uitvoerbare bestanden blokkeren, tenzij ze voldoen aan een criteria voor gebruik, leeftijd of vertrouwde lijst | 01443614-cd74-433a-b99e-2ecdc07bfc25
Geavanceerde beveiliging tegen ransomware gebruiken | c1db55ab-c21a-4637-bb3f-a12568109d35
Referenties van het windows-subsysteem van de lokale beveiligingsinstantie blokkeren (lsass.exe) | 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2
Procescreaties blokkeren die afkomstig zijn van PSExec- en WMI-opdrachten | d1e49aac-8f56-4280-b9ba-993a6d77406c
Niet-vertrouwde en niet-ondertekende processen blokkeren die worden uitgevoerd via USB | b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4
Office-communicatietoepassingen blokkeren om onderliggende processen te maken | 26190899-1602-49e8-8b27-eb1d0a1ce869
Adobe Reader blokkeren om onderliggende processen te maken | 7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c
Persistentie blokkeren via WMI-gebeurtenisabonnement | e6db77e5-3df2-4cf1-b95a-636979351e5b

Zie het [onderwerp Aanvalsoppervlakverkorting](attack-surface-reduction.md) voor meer informatie over elke regel.

### <a name="use-group-policy-to-exclude-files-and-folders"></a>Groepsbeleid gebruiken om bestanden en mappen uit te sluiten

1. Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.** [](https://technet.microsoft.com/library/cc731212.aspx)

2. Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie** en klik op **Beheersjablonen.**

3. Vouw de boom uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Windows Defender Exploit  >  **Guard** Attack  >  **surface reduction**.

4. Dubbelklik op de **instelling Bestanden en paden uitsluiten van de** instelling Surface Reduction Rules van Attack en stel de optie in op **Ingeschakeld.** Selecteer **Weergeven** en voer elk bestand of elke map in de kolom **Waardenaam** in. Voer **0** in de kolom **Waarde** in voor elk item.

> [!WARNING]
> Gebruik geen aanhalingstekens omdat deze niet worden ondersteund voor de kolom **Waardenaam** of **Waarde.**

### <a name="use-powershell-to-exclude-files-and-folders"></a>PowerShell gebruiken om bestanden en mappen uit te sluiten

1. Typ **powershell** in het menu Start, klik met de rechtermuisknop op **Windows PowerShell en** selecteer Uitvoeren als **beheerder**
2. Voer de volgende cmdlet in:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

Blijf gebruiken om `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` meer mappen toe te voegen aan de lijst.

> [!IMPORTANT]
> Gebruik deze app om apps toe te voegen `Add-MpPreference` of toe te voegen aan de lijst. Als u `Set-MpPreference` de cmdlet gebruikt, wordt de bestaande lijst overschreven.

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>MDM-CSP's gebruiken om bestanden en mappen uit te sluiten

Gebruik [de CSP (Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider) om uitsluitingen toe te voegen.

## <a name="customize-the-notification"></a>De melding aanpassen

U kunt de melding aanpassen voor wanneer een regel wordt geactiveerd en een app of bestand blokkeert. Zie het [windows-beveiligingsartikel.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)

## <a name="related-topics"></a>Verwante onderwerpen

* [Aanvalsoppervlakken verminderen met regels voor het beperken van de surface van de aanval](attack-surface-reduction.md)
* [Regels voor het verlagen van de surface voor aanvallen inschakelen](enable-attack-surface-reduction.md)
* [Regels voor het verlagen van het oppervlak van de aanval evalueren](evaluate-attack-surface-reduction.md)
* [Veelgestelde vragen over surface reduction attack](attack-surface-reduction.md)
