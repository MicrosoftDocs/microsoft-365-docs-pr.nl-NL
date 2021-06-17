---
title: Gebeurtenissen voor het verminderen van kwetsbaarheid voor aanvallen bekijken
description: Importeer aangepaste weergaven om gebeurtenissen in de surface-beperking van aanvallen te zien.
keywords: event view, exploit guard, audit, review, events
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
ms.openlocfilehash: f8de3d8b2d7c07f8d783ecbe85b7e4a9c612aae5
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985451"
---
# <a name="view-attack-surface-reduction-events"></a>Gebeurtenissen voor het verminderen van kwetsbaarheid voor aanvallen bekijken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Controleer gebeurtenissen met een beperking van de surface attack in Event Viewer om te controleren welke regels of instellingen werken. U kunt ook bepalen of instellingen te 'luidruchtig' zijn of van invloed zijn op uw dagelijkse werkstroom.

Het controleren van gebeurtenissen is handig wanneer u de functies evalueert. U kunt de auditmodus inschakelen voor functies of instellingen en vervolgens controleren wat er zou zijn gebeurd als ze volledig waren ingeschakeld.

In dit artikel worden alle gebeurtenissen, de bijbehorende functie of instelling beschreven en wordt beschreven hoe u aangepaste weergaven kunt maken om te filteren op specifieke gebeurtenissen.

Krijg gedetailleerde rapportage over gebeurtenissen, blokken en waarschuwingen als onderdeel van Windows-beveiliging als u een E5-abonnement hebt en [Microsoft Defender voor Eindpunt gebruikt.](microsoft-defender-endpoint.md)

## <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a>Aangepaste weergaven gebruiken om de mogelijkheden voor het verminderen van de Surface-aanval te bekijken

Maak aangepaste weergaven in de Windows Viewer voor gebeurtenissen om alleen gebeurtenissen te zien voor specifieke mogelijkheden en instellingen. De eenvoudigste manier is om een aangepaste weergave te importeren als een XML-bestand. U kunt de XML rechtstreeks vanaf deze pagina kopiëren.

U kunt ook handmatig naar het gebeurtenisgebied navigeren dat overeenkomt met de functie.

### <a name="import-an-existing-xml-custom-view"></a>Een bestaande aangepaste XML-weergave importeren

1. Maak een leeg .txt bestand en kopieer de XML voor de aangepaste weergave die u wilt gebruiken in het .txt bestand. Doe dit voor elk van de aangepaste weergaven die u wilt gebruiken. Wijzig de naam van de bestanden als volgt (zorg ervoor dat u het type wijzigt van .txt in .xml):
    - Aangepaste weergave gecontroleerde *maptoegangsgebeurtenissen:cfa-events.xml*
    - Aangepaste weergave beveiligingsgebeurtenissen *gebruiken:ep-events.xml*
    - Aangepaste weergave Voor surface reduction events van attack: *asr-events.xml*
    - Aangepaste weergave netwerk- en *beveiligingsgebeurtenissen:np-events.xml*

2. Typ **gebeurtenisviewer** in de Startmenu en open **Gebeurtenisviewer.**

3. Selecteer **Aangepaste**  >  **weergave actie importeren...**

  > [!div class="mx-imgBorder"]
  > ![Animatie die aangepaste weergave importeren aan de linkerkant van het venster Even viewer markeert](images/events-import.gif)

4. Ga naar de plaats waar u XML-bestand hebt geëxtraheerd voor de aangepaste weergave die u wilt gebruiken en selecteer het.

5. Selecteer **Openen**.

6. Er wordt een aangepaste weergave gemaakt waarmee alleen de gebeurtenissen met betrekking tot die functie worden gefilterd.

### <a name="copy-the-xml-directly"></a>De XML rechtstreeks kopiëren

1. Typ **gebeurtenisviewer** in de Startmenu en open de Windows **Viewer voor gebeurtenissen.**

2. Selecteer in het linkervenster onder **Acties** de optie **Aangepaste weergave maken...**

  > [!div class="mx-imgBorder"]
  > ![Animatie met de optie Aangepaste weergave maken in het venster Gebeurtenisviewer](images/events-create.gif)

3. Ga naar het tabblad XML en selecteer **Query handmatig bewerken.** U ziet een waarschuwing dat u de query niet kunt bewerken met het tabblad **Filter** als u de optie XML gebruikt. Selecteer **Ja**.

4. Plak de XML-code voor de functie die u wilt filteren op gebeurtenissen in de XML-sectie.

5. Selecteer **OK**. Geef een naam op voor het filter. Hiermee wordt een aangepaste weergave gemaakt waarmee alleen de gebeurtenissen met betrekking tot die functie worden gefilterd.

### <a name="xml-for-attack-surface-reduction-rule-events"></a>XML voor regelgebeurtenissen voor aanvalsoppervlakbeperking

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-controlled-folder-access-events"></a>XML voor beheerde maptoegangsgebeurtenissen

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-exploit-protection-events"></a>XML voor exploitbeveiligingsgebeurtenissen

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Security-Mitigations/KernelMode">
   <Select Path="Microsoft-Windows-Security-Mitigations/KernelMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Concurrency">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Contention">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Messages">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Operational">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Power">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Render">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Tracing">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/UIPI">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="System">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Security-Mitigations/UserMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-network-protection-events"></a>XML voor netwerkbeveiligingsgebeurtenissen

```xml
<QueryList>
 <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
  <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
  <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
 </Query>
</QueryList>
```

## <a name="list-of-attack-surface-reduction-events"></a>Lijst met gebeurtenissen in de beperking van de aanvalsoppervlakken

Alle gebeurtenissen voor het verminderen van aanvallen bevinden zich onder Applications **and Services Logs > Microsoft > Windows** en vervolgens de map of provider zoals vermeld in de volgende tabel.

U hebt toegang tot deze gebeurtenissen in Windows Viewer voor gebeurtenissen:

1. Open het **menu Start** en typ **de gebeurtenisviewer** en selecteer het **resultaat van de gebeurtenisviewer.**
2. Vouw **toepassingen en serviceslogboeken > Microsoft > Windows** uit en ga naar de map die wordt weergegeven onder **Provider/bron** in de onderstaande tabel.
3. Dubbelklik op het subitem om gebeurtenissen te zien. Blader door de gebeurtenissen om de gebeurtenissen te vinden die u zoekt.

   ![Animatie met behulp van Gebeurtenisviewer](images/event-viewer.gif)

Functie | Provider/bron | Gebeurtenis-id | Beschrijving
:-|:-|:-:|:-
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 1 | ACG-audit
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 2 | ACG afdwingen
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 3 | Controle van onderliggende processen niet toestaan
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 4 | Blokkering van onderliggende processen niet toestaan
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 5 | Controle van afbeeldingen met lage integriteit blokkeren
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 6 | Blokkering van afbeeldingen met lage integriteit
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 7 | Externe afbeeldingen controleren blokkeren
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 8 | Blokkering van externe afbeeldingen blokkeren
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 9 | Controle van win32k-systeemoproepen uitschakelen
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 10 | Win32k-systeemoproepen blokkeren uitschakelen
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 11 | Controle van de codeintegriteitscontrole
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 12 | Code integrity guard block
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 13 | EAF-audit
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 14 | EAF afdwingen
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 15 | EAF+-audit
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 16 | EAF+ afdwingen
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 17 | IAF-audit
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 18 | IAF afdwingen
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 19 | ROP StackPivot-audit
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 20 | ROP StackPivot afdwingen
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 21 | ROP-bellerControle
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 22 | ROP CallerCheck afdwingen
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 23 | ROP SimExec-audit
Bescherming tegen misbruik | Security-Mitigations (kernelmodus/gebruikersmodus) | 24 | ROP SimExec afdwingen
Bescherming tegen misbruik | WER-Diagnostics | 5 | CFG-blok
Bescherming tegen misbruik | Win32K (operationeel) | 260 | Niet-vertrouwd lettertype
Netwerkbeveiliging | Windows Defender (operationeel) | 5007 | Gebeurtenis wanneer instellingen worden gewijzigd
Netwerkbeveiliging | Windows Defender (operationeel) | 1125 | Gebeurtenis wanneer netwerkbeveiliging wordt uitgevoerd in de auditmodus
Netwerkbeveiliging | Windows Defender (operationeel) | 1126 | Gebeurtenis wanneer netwerkbeveiliging wordt branden in de blokmodus
Beheerde maptoegang | Windows Defender (operationeel) | 5007 | Gebeurtenis wanneer instellingen worden gewijzigd
Beheerde maptoegang | Windows Defender (operationeel) | 1124 | Gecontroleerde gebeurtenis gecontroleerde maptoegang
Beheerde maptoegang | Windows Defender (operationeel) | 1123 | Gebeurtenis Geblokkeerde gecontroleerde maptoegang
Beheerde maptoegang | Windows Defender (operationeel) | 1127 | Gebeurtenis geblokkeerde gecontroleerde maptoegangssector schrijfblok
Beheerde maptoegang | Windows Defender (operationeel) | 1128 | Gecontroleerde beheerde maptoegang sector schrijfblokgebeurtenis
Kwetsbaarheid voor aanvallen verminderen | Windows Defender (operationeel) | 5007 | Gebeurtenis wanneer instellingen worden gewijzigd
Kwetsbaarheid voor aanvallen verminderen | Windows Defender (operationeel) | 1122 | Gebeurtenis wanneer regel wordt branden in de auditmodus
Kwetsbaarheid voor aanvallen verminderen | Windows Defender (operationeel) | 1121 | Gebeurtenis wanneer regel wordt branden in de blokmodus
