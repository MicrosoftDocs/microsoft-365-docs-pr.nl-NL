---
title: Potentieel ongewenste toepassingen blokkeren met Microsoft Defender Antivirus
description: Schakel de mogelijk ongewenste toepassing (PUA) antivirusfunctie in om ongewenste software, zoals adware, te blokkeren.
keywords: pua, inschakelen, ongewenste software, ongewenste apps, werkbalk van de browser, detecteren, blokkeren, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: mimilone, julih
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/02/2021
ms.openlocfilehash: d7f411c81e839d3929d4aa1a52fda29399c59dca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772375"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>Mogelijk ongewenste toepassingen detecteren en blokkeren

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

Mogelijk ongewenste toepassingen (PUA) zijn een softwarecategorie die ervoor kan zorgen dat uw computer vertraagt, onverwachte advertenties weergeeft of in het slechtste geval andere software installeert die onverwacht of ongewenst is. PUA wordt niet beschouwd als een virus, malware of ander type bedreiging, maar kan acties uitvoeren op eindpunten die de prestaties of het gebruik van eindpunten nadelig beïnvloeden. De term *PUA* kan ook verwijzen naar een toepassing met een slechte reputatie, zoals beoordeeld door Microsoft Defender voor Eindpunt, vanwege bepaalde soorten ongewenste gedragingen.

Dit zijn enkele voorbeelden:

- **Reclamesoftware** waarop advertenties of promoties worden weergegeven, waaronder software waarmee advertenties op webpagina's worden geplaatst.
- **Installatiesoftware** die aanbiedt andere software te installeren die niet digitaal is ondertekend door dezelfde entiteit. En ook software die aanbiedt om andere software te installeren die aangemerkt kan worden als PUA.
- **Ontduikingssoftware** die actief probeert detectie door beveiligingsproducten te ontduiken, waaronder software die zich anders gedraagt in de aanwezigheid van beveiligingsproducten.

> [!TIP]
> Zie voor meer voorbeelden en een discussie over de criteria die we gebruiken bij het labelen van toepassingen voor speciale aandacht van beveiligingsfuncties [Hoe Microsoft malware en mogelijk ongewenste toepassingen identificeert](/windows/security/threat-protection/intelligence/criteria).

Mogelijk ongewenste toepassingen kunnen het risico vergroten dat uw netwerk wordt geïnfecteerd met werkelijke malware, ervoor zorgen dat malware minder goed te herkennen is of dat IT-resources worden verspild bij het verwijderen ervan. PUA-beveiliging wordt ondersteund in Windows 10, Windows Server 2019 en Windows Server 2016. In Windows 10 (versie 2004 en hoger) blokkeert Microsoft Defender Antivirus apps die standaard worden beschouwd als PUA voor Enterprise-apparaten (E5).

## <a name="microsoft-edge"></a>Microsoft Edge

Met [het nieuwe Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), dat op Chromium is gebaseerd, blokkeert u mogelijk ongewenste toepassingsdownloads en bijbehorende resource-URL's. Deze functie is beschikbaar via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>PUA-beveiliging inschakelen in het op Chromium gebaseerde Microsoft Edge

Hoewel mogelijk ongewenste toepassingsbeveiliging in Microsoft Edge (gebaseerd op Chromium, versie 80.0.361.50) standaard is uitgeschakeld, kan dit eenvoudig vanuit de browser worden ingeschakeld.

1. Selecteer de drie puntjes in uw Microsoft Edge-browser en kies vervolgens **Instellingen**.

2. Selecteer **privacy, zoekopdrachten en services**.

3. Schakel onder de sectie **Beveiliging** **Mogelijk ongewenste apps blokkeren** in.

> [!TIP]
> Als u Microsoft Edge (Gebaseerd op Chromium) gebruikt, kunt u de functie voor URL-blokkering van PUA-beveiliging verkennen door deze te testen op een van onze [Microsoft Defender SmartScreen-demopagina's](https://demo.smartscreen.msft.net/).

### <a name="block-urls-with-microsoft-defender-smartscreen"></a>URL's blokkeren met Microsoft Defender SmartScreen

In het op Chromium gebaseerde Microsoft Edge met PUA-beveiliging ingeschakeld, beschermt Microsoft Defender SmartScreen u tegen URL's die aan PUA zijn gekoppeld.

Beveiligingsbeheerders kunnen [configureren](/DeployEdge/configure-microsoft-edge) hoe Microsoft Edge en Microsoft Defender SmartScreen samenwerken om groepen gebruikers te beschermen tegen URL's die aan PUA zijn gekoppeld. Er zijn verschillende [instellingen voor groepsbeleid](/DeployEdge/microsoft-edge-policies#smartscreen-settings) expliciet beschikbaar voor Microsoft Defender SmartScreen, waaronder [voor het blokkeren van PUA-](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled). Daarnaast kunnen beheerders [Microsoft Defender SmartScreen-](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) configureren met groepsbeleidsinstellingen om Microsoft Defender SmartScreen in of uit te schakelen.

Hoewel Microsoft Defender voor Eindpunt een eigen blokkeringslijst heeft op basis van een gegevensset die wordt beheerd door Microsoft, kunt u deze lijst aanpassen op basis van uw eigen bedreigingsinformatie. Als u in de portal van Microsoft Defender voor Eindpunt [indicatoren maakt en beheert](manage-indicators.md), respecteert Microsoft Defender SmartScreen de nieuwe instellingen.

## <a name="microsoft-defender-antivirus-and-pua-protection"></a>Microsoft Defender Antivirus en PUA-beveiliging

Met de beveiligingsfunctie voor mogelijk ongewenste toepassingen (PUA) in Microsoft Defender Antivirus kunt u PUA detecteren en blokkeren voor eindpunten in uw netwerk.

> [!NOTE]
> Deze functie is beschikbaar in Windows 10, Windows Server 2019 en Windows Server 2016.

Microsoft Defender Antivirus blokkeert PUA-bestanden en pogingen om ze te downloaden, te verplaatsen, uit te voeren of te installeren. Geblokkeerde PUA-bestanden worden vervolgens in quarantaine geplaatst. Wanneer een PUA-bestand wordt aangetroffen op een eindpunt, stuurt Microsoft Defender Antivirus een melding naar de gebruiker ([tenzij meldingen zijn uitgeschakeld](configure-notifications-microsoft-defender-antivirus.md)) in dezelfde indeling als andere bedreigingsdetecties. De melding wordt voorafgegaan door `PUA:` om de inhoud aan te geven.

De melding wordt weergegeven in de gebruikelijke [quarantainelijst in de app voor Windows-beveiliging](microsoft-defender-security-center-antivirus.md).

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>PUA-beveiliging configureren in Microsoft Defender Antivirus

U kunt PUA-beveiliging inschakelen met [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Groepsbeleid](/azure/active-directory-domain-services/manage-group-policy)of via [PowerShell-cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).

U kunt PUA-beveiliging ook gebruiken in de controlemodus om mogelijk ongewenste toepassingen te detecteren zonder deze te blokkeren. De detecties worden vastgelegd in het gebeurtenislogboek van Windows.

> [!TIP]
> Ga naar de demowebsite van Microsoft Defender voor Eindpunt op [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) om te bevestigen dat de functie werkt en deze in actie te zien.

PUA-beveiliging in de controlemodus is handig als uw bedrijf een interne controle op de naleving van softwarebeveiliging uitvoert en u fout-positieven wilt voorkomen.

### <a name="use-intune-to-configure-pua-protection"></a>Intune gebruiken om PUA-beveiliging te configureren

Zie [Instellingen voor apparaatbeperkingen configureren in Microsoft Intune](/intune/device-restrictions-configure) en [Microsoft Defender Antivirus-apparaatbeperkingsinstellingen voor Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) voor meer informatie.

### <a name="use-configuration-manager-to-configure-pua-protection"></a>Configuration Manager gebruiken om PUA-beveiliging te configureren

PUA-beveiliging is standaard ingeschakeld in Microsoft Endpoint Manager (Current Branch).

Zie [Hoe u antimalwarebeleid kunt maken en implementeren: Instellingen voor geplande scans](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) voor meer informatie over het configureren van Microsoft Endpoint Manager (Current Branch).

Zie [Hoe beleid voor het beveiligen tegen mogelijk ongewenste toepassingen te implementeren voor eindpuntbeveiliging in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA) voor System Center 2012 Configuration Manager.

> [!NOTE]
> PUA-gebeurtenissen die worden geblokkeerd door Microsoft Defender Antivirus, worden gerapporteerd in de Windows Event Viewer en niet in Microsoft Endpoint Configuration Manager.

### <a name="use-group-policy-to-configure-pua-protection"></a>Groepsbeleid gebruiken om PUA-beveiliging te configureren

1. Download en installeer [Beheersjablonen (.admx) voor Windows 10 update van oktober 2020 (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)

2. Open op uw computer voor groepsbeleidsbeheer de [Console groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

3. Selecteer het groepsbeleidsobject dat u wilt configureren en kies **Bewerken**.

4. Ga in de **Groepsbeleidsbeheereditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen**.

5. Vouw de boomstructuur uit naar **Windows-onderdelen** > **Microsoft Defender Antivirus**.

6. Dubbelklik op **Detectie configureren voor mogelijk ongewenste toepassingen**.

7. Selecteer **Inschakelen** om PUA-beveiliging in te schakelen.

8. In **Opties** selecteert u **Blokkeren** om mogelijk ongewenste toepassingen te blokkeren of selecteert u **Auditmodus** om te testen hoe de instelling werkt in uw omgeving. Kies **OK**.

9. Implementeer uw groepsbeleidsobject zoals u dat gewoonlijk doet.

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>PowerShell-cmdlets gebruiken om PUA-beveiliging te configureren

#### <a name="to-enable-pua-protection"></a>Om PUA-beveiliging in te schakelen

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

Als u de waarde voor deze cmdlet instelt op `Enabled` schakelt u de functie in als deze is uitgeschakeld.

#### <a name="to-set-pua-protection-to-audit-mode"></a>PUA-beveiliging instellen op controlemodus

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

Door in te stellen op `AuditMode` worden PUA's gedetecteerd zonder ze te blokkeren.

#### <a name="to-disable-pua-protection"></a>Om PUA-beveiliging uit te schakelen

U wordt aangeraden PUA-beveiliging ingeschakeld te laten. U kunt de cmdlet echter uitschakelen met behulp van de volgende cmdlet:

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

Als u de waarde voor deze cmdlet instelt op `Disabled` schakelt u de functie uit als deze is ingeschakeld.

Zie [PowerShell-cmdlets gebruiken om Microsoft Defender Antivirus te configureren en uit te voeren](use-powershell-cmdlets-microsoft-defender-antivirus.md) en [Defender-cmdlets](/powershell/module/defender/index) voor meer informatie.

## <a name="view-pua-events-using-powershell"></a>PUA-gebeurtenissen weergeven met PowerShell

PUA-gebeurtenissen worden gerapporteerd in Windows Event Viewer, maar niet in Microsoft Endpoint Manager of in Intune. U kunt de `Get-MpThreat` cmdlet ook gebruiken om bedreigingen te bekijken die door Microsoft Defender Antivirus zijn verwerkt. Hier volgt een voorbeeld:

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

## <a name="get-email-notifications-about-pua-detections"></a>Meldingen per e-mail ontvangen over PUA-detecties

U kunt e-mailmeldingen inschakelen om e-mail over PUA-detecties te ontvangen.

Zie [Probleemoplossing van gebeurtenis-id's](troubleshoot-microsoft-defender-antivirus.md) voor meer informatie over het weergeven van Microsoft Defender Antivirus-gebeurtenissen. PUA-gebeurtenissen worden vastgelegd onder gebeurtenis-id **1160**.

## <a name="view-pua-events-using-advanced-hunting"></a>PUA-evenementen bekijken met geavanceerde opsporing

Als u [Microsoft Defender voor Eindpunt](microsoft-defender-endpoint.md)gebruikt, kunt u een geavanceerde opsporingsquery uitvoeren om PUA-evenementen te bekijken. Hier volgt een voorbeeldquery:

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName = tostring(x.ThreatName), WasExecutingWhileDetected = tostring(x.WasExecutingWhileDetected), WasRemediated = tostring(x.WasRemediated)
| where ThreatName startswith_cs 'PUA:'
```

Zie voor meer informatie over geavanceerde opsporing [Proactief zoeken op bedreigingen met geavanceerde opsporing](advanced-hunting-overview.md).

## <a name="exclude-files-from-pua-protection"></a>Bestanden uitsluiten van PUA-beveiliging

Soms wordt een bestand ten onrechte geblokkeerd door PUA-beveiliging of is een functie van een PUA vereist om een taak te voltooien. In deze gevallen kan een bestand worden toegevoegd aan een lijst met uitsluitingen.

Zie voor meer informatie [Uitgesloten items configureren en valideren op basis van de bestandsextensie en maplocatie](configure-extension-file-exclusions-microsoft-defender-antivirus.md).

## <a name="see-also"></a>Zie ook

- [Beveiliging van de volgende generatie](microsoft-defender-antivirus-in-windows-10.md)
- [Gedragsmatige, heuristieke en realtimebescherming configureren](configure-protection-features-microsoft-defender-antivirus.md)