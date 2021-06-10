---
title: Regels voor het verminderen van aanvalsoppervlakken aanpassen
description: Stel afzonderlijk regels in audit-, blok- of uitgeschakelde modi in en voeg bestanden en mappen toe die moeten worden uitgesloten van de regels voor de beperking van het aanvalsoppervlak
keywords: Aanvalsoppervlakverminding, hips, host intrusion prevention system, protection rules, anti-exploit, anti-exploit, exploit, infection prevention, customize, configure, exclude
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: c03bc2a61ba2dae1b5db34c6b48d623c58c0c613
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782871"
---
# <a name="customize-attack-surface-reduction-rules"></a>Regels voor het verminderen van aanvalsoppervlakken aanpassen

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.

[Met surface reduction-regels voor aanvallen](enable-attack-surface-reduction.md) kunt u voorkomen dat softwaregedrag vaak wordt misbruikt om uw apparaat of netwerk in gevaar te brengen. Een aanvaller kan bijvoorbeeld proberen een niet-ondertekend script uit te voeren op een USB-station of een macro in een Office-document rechtstreeks laten bellen naar de Win32-API. Regels voor het beperken van het oppervlak van aanvallen kunnen dit soort riskante gedragingen beperken en de defensieve houding van uw organisatie verbeteren.

Lees hoe u regels voor [](#exclude-files-and-folders) het verminderen van [](#customize-the-notification) aanvallen kunt aanpassen door bestanden en mappen uit te sluiten of aangepaste tekst toe te voegen aan de meldingsmelding die op de computer van een gebruiker wordt weergegeven.

U kunt regels voor de beperking van de surface voor aanvallen instellen voor apparaten met een van de volgende versies en versies van Windows:
- Windows 10 Pro, versie [1709](/windows/whats-new/whats-new-windows-10-version-1709) of hoger
- Windows 10 Enterprise, versie [1709](/windows/whats-new/whats-new-windows-10-version-1709) of hoger
- Windows Server, [versie 1803 (halfjaarlijks kanaal)](/windows-server/get-started/whats-new-in-windows-server-1803) of hoger
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19) U kunt group policy, PowerShell en Mobile Device Management (MDM) configuration service providers (CSP) gebruiken om deze instellingen te configureren.

## <a name="exclude-files-and-folders"></a>Bestanden en mappen uitsluiten

U kunt ervoor kiezen om uit te sluiten dat bestanden en mappen worden geëvalueerd door regels voor het verminderen van het oppervlak van de aanval. Wanneer het bestand is uitgesloten, wordt het niet geblokkeerd, zelfs niet als een surface reduction-regel voor aanvallen detecteert dat het bestand schadelijk gedrag bevat.

Denk bijvoorbeeld aan de ransomware-regel:

De ransomware-regel is ontworpen om zakelijke klanten te helpen de risico's van ransomware-aanvallen te beperken en tegelijkertijd de bedrijfscontinuïteit te waarborgen. Standaard wordt de ransomware-regel als waarschuwing gebruikt en beschermd tegen bestanden die nog niet voldoende reputatie en vertrouwen hebben bereikt. Om de nadruk te herstellen, wordt de ransomware-regel alleen triggers voor bestanden die onvoldoende positieve reputatie en prevalentie hebben verkregen, op basis van gebruiksgegevens van miljoenen van onze klanten. Meestal worden de blokken zelf opgelost, omdat de waarden 'reputatie en vertrouwen' van elk bestand stapsgewijs worden bijgewerkt naarmate het niet-problematische gebruik toeneemt.

In gevallen waarin blokken niet tijdig zelf worden opgelost, kunnen klanten _-_ op eigen risico - gebruikmaken van het selfservicemechanisme of een op IOC (Indicator of Compromise) gebaseerde 'lijst met toegestane bestanden' om de blokkering van de bestanden zelf te deblokkeren.  

> [!WARNING]
> Het uitsluiten of deblokkeren van bestanden of mappen kan mogelijk onveilige bestanden toestaan om uw apparaten uit te voeren en te infecteren. Het uitsluiten van bestanden of mappen kan de beveiliging die wordt geboden door regels voor het beperken van het oppervlak van de aanval, aanzienlijk beperken. Bestanden die door een regel zijn geblokkeerd, kunnen worden uitgevoerd en er wordt geen rapport of gebeurtenis opgenomen.

Een uitsluiting is van toepassing op alle regels die uitsluitingen toestaan. U kunt een afzonderlijk bestand, mappad of de volledig gekwalificeerde domeinnaam voor een resource opgeven. U kunt een uitsluiting echter niet beperken tot een specifieke regel.

Een uitsluiting wordt alleen toegepast wanneer de uitgesloten toepassing of service wordt gestart. Als u bijvoorbeeld een uitsluiting toevoegt voor een updateservice die al wordt uitgevoerd, blijft de updateservice gebeurtenissen activeren totdat de service is gestopt en opnieuw wordt gestart.

Attack Surface Reduction ondersteunt omgevingsvariabelen en jokertekens. Zie Jokertekens gebruiken in de lijsten met bestandsnaam en mappaden of [uitbreidingsuitsluitingen](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) voor informatie over het gebruik van jokertekens.
Als u problemen ondervindt met regels voor het detecteren van bestanden die volgens u niet moeten worden gedetecteerd, gebruikt u de auditmodus om [de regel te testen.](evaluate-attack-surface-reduction.md)

| Beschrijving van regel | GUID |
|:----|:----|
| Alle toepassingen Office voor het maken van onderliggende processen blokkeren | `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` |
| De uitvoering van mogelijk obfuscated scripts blokkeren | `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC` |
| Win32 API-oproepen blokkeren vanuit Office macro | `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B` |
| Voorkomen Office het maken van uitvoerbare inhoud | `3B576869-A4EC-4529-8536-B80A7769E899` |
| Het Office blokkeren om code in andere processen te injecteren | `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84` |
| JavaScript of VBScript blokkeren om gedownloade uitvoerbare inhoud te starten | `D3E037E1-3EB8-44C8-A917-57927947596D` |
| Uitvoerbare inhoud van e-mailclient en webmail blokkeren | `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550` |
| Het uitvoeren van uitvoerbare bestanden blokkeren, tenzij ze voldoen aan een criteria voor gebruik, leeftijd of vertrouwde lijst | `01443614-cd74-433a-b99e-2ecdc07bfc25` |
| Geavanceerde beveiliging tegen ransomware gebruiken | `c1db55ab-c21a-4637-bb3f-a12568109d35` |
| Referenties van het subsysteem van de Windows lokale beveiligingsinstantie blokkeren (lsass.exe) | `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2` |
| Procescreaties blokkeren die afkomstig zijn van PSExec- en WMI-opdrachten | `d1e49aac-8f56-4280-b9ba-993a6d77406c` |
| Niet-vertrouwde en niet-ondertekende processen blokkeren die worden uitgevoerd via USB | `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4` |
| Het Office communicatietoepassingen blokkeren om onderliggende processen te maken | `26190899-1602-49e8-8b27-eb1d0a1ce869` |
| Adobe Reader blokkeren om onderliggende processen te maken | `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c` |
| Persistentie blokkeren via WMI-gebeurtenisabonnement | `e6db77e5-3df2-4cf1-b95a-636979351e5b` |

Zie het [onderwerp Aanvalsoppervlakverkorting](attack-surface-reduction.md) voor meer informatie over elke regel.

### <a name="use-group-policy-to-exclude-files-and-folders"></a>Groepsbeleid gebruiken om bestanden en mappen uit te sluiten

1. Open op uw computer voor groepsbeleidsbeheer de [Groepsbeleidsbeheerconsole](https://technet.microsoft.com/library/cc731212.aspx), klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken**.

2. Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie** en klik op **Beheersjablonen.**

3. Vouw de boom uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **Windows Defender Exploit Guard** Attack surface  >  **reduction**.

4. Dubbelklik op de **instelling Bestanden en paden uitsluiten van de** instelling Surface Reduction Rules van Attack en stel de optie in op **Ingeschakeld.** Selecteer **Weergeven** en voer elk bestand of elke map in de kolom **Waardenaam** in. Voer **0** in de kolom **Waarde** in voor elk item.

> [!WARNING]
> Gebruik geen aanhalingstekens omdat deze niet worden ondersteund voor de kolom **Waardenaam** of **Waarde.**

### <a name="use-powershell-to-exclude-files-and-folders"></a>PowerShell gebruiken om bestanden en mappen uit te sluiten

1. Typ **powershell** in het menu Start, klik met de **rechtermuisknop Windows PowerShell** en selecteer Uitvoeren als **beheerder**
2. Voer de volgende cmdlet in:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

Blijf gebruiken om `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` meer mappen toe te voegen aan de lijst.

> [!IMPORTANT]
> Gebruik deze app om apps toe te voegen `Add-MpPreference` of toe te voegen aan de lijst. Als u `Set-MpPreference` de cmdlet gebruikt, wordt de bestaande lijst overschreven.

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>MDM-CSP's gebruiken om bestanden en mappen uit te sluiten

Gebruik [de CSP (Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider) om uitsluitingen toe te voegen.

## <a name="customize-the-notification"></a>De melding aanpassen

U kunt de melding aanpassen voor wanneer een regel wordt geactiveerd en een app of bestand blokkeert. Zie het [Windows-beveiliging](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center) artikel.

## <a name="related-topics"></a>Verwante onderwerpen

* [Aanvalsoppervlakken verminderen met regels voor het beperken van de surface van de aanval](attack-surface-reduction.md)
* [Regels voor het verminderen van aanvalsoppervlakken inschakelen](enable-attack-surface-reduction.md)
* [Regels voor het verminderen van kwetsbaarheid voor aanvallen evalueren](evaluate-attack-surface-reduction.md)
* [Veelgestelde vragen over het verminderen van kwetsbaarheid voor aanvallen](attack-surface-reduction.md)
