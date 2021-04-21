---
title: Mogelijk ongewenste toepassingen blokkeren met Microsoft Defender Antivirus
description: Schakel de antivirusfunctie voor potentieel ongewenste toepassing (PUA) in om ongewenste software, zoals adware, te blokkeren.
keywords: pua, enable, ongewenste software, ongewenste apps, malware, browserwerkbalk, detecteren, blokkeren, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 808eff2074dfe1573708264590b401f3d38db982
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904008"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>Potentieel ongewenste toepassingen detecteren en blokkeren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

Potentieel ongewenste toepassingen (PUA) zijn een categorie software waarmee uw computer traag kan worden uitgevoerd, onverwachte advertenties kan weergeven of in het slechtste geval andere software kan installeren die onverwacht of ongewenst kan zijn. PUA wordt niet beschouwd als een virus, malware of ander type bedreiging, maar het kan acties uitvoeren op eindpunten die de prestaties of het gebruik van eindpunten nadelig beïnvloeden. De term *PUA kan* ook verwijzen naar een toepassing met een slechte reputatie, zoals beoordeeld door Microsoft Defender voor Eindpunt, vanwege bepaalde soorten ongewenst gedrag.

Dit zijn enkele voorbeelden:

- **Reclamesoftware** waarmee advertenties of promoties worden weergegeven, inclusief software waarmee advertenties op webpagina's worden geplaatst.
- **Bundeling van software die** biedt voor het installeren van andere software die niet digitaal is ondertekend door dezelfde entiteit. Ook software die biedt voor het installeren van andere software die in aanmerking komt als PUA.
- **Software voor ontwijking** die actief probeert detectie door beveiligingsproducten te omzeilen, inclusief software die zich anders gedraagt in aanwezigheid van beveiligingsproducten.

> [!TIP]
> Zie Hoe Microsoft malware en potentieel ongewenste toepassingen identificeert voor meer voorbeelden en een bespreking van de criteria die we gebruiken om toepassingen te labelen voor speciale aandacht van [beveiligingsfuncties.](/windows/security/threat-protection/intelligence/criteria)

Mogelijk ongewenste toepassingen kunnen het risico vergroten dat uw netwerk wordt geïnfecteerd met werkelijke malware, malware-infecties moeilijker te identificeren of IT-bronnen verspillen door ze op te ruimen. PUA-beveiliging wordt ondersteund in Windows 10, Windows Server 2019 en Windows Server 2016. In Windows 10 (versie 2004 en hoger) blokkeert Microsoft Defender Antivirus apps die standaard worden beschouwd als PUA voor Enterprise-apparaten (E5).

## <a name="microsoft-edge"></a>Microsoft Edge

De [nieuwe Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), die op Chromium is gebaseerd, blokkeert mogelijk ongewenste toepassingsdownloads en bijbehorende resource-URL's. Deze functie wordt geleverd via [Microsoft Defender SmartScreen.](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>PUA-beveiliging inschakelen in microsoft edge op basis van Chromium

Hoewel mogelijk ongewenste toepassingsbeveiliging in Microsoft Edge (op Chromium gebaseerde versie 80.0.361.50) standaard is uitgeschakeld, kan deze eenvoudig vanuit de browser worden ingeschakeld.

1. Selecteer in de Edge-browser de drie puntjes en kies vervolgens **Instellingen.**

2. Selecteer **Privacy, zoeken en services.**

3. Schakel onder **de sectie** Beveiliging mogelijk ongewenste apps **blokkeren in.**

> [!TIP]
> Als u Microsoft Edge (op Chromium gebaseerd) gebruikt, kunt u de URL-blokkeringsfunctie van PUA-beveiliging veilig verkennen door deze uit te testen op een van onze [Microsoft Defender SmartScreen-demopagina's.](https://demo.smartscreen.msft.net/)

### <a name="block-urls-with-microsoft-defender-smartscreen"></a>URL's blokkeren met Microsoft Defender SmartScreen

In op Chromium gebaseerde Edge met PUA-beveiliging ingeschakeld, beschermt Microsoft Defender SmartScreen u tegen URL's die aan PUA zijn gekoppeld.

Beveiligingsbeheerders kunnen [configureren hoe](/DeployEdge/configure-microsoft-edge) Microsoft Edge en Microsoft Defender SmartScreen samenwerken om groepen gebruikers te beschermen tegen URL's die aan PUA zijn gekoppeld. Er zijn verschillende [groepsbeleidsinstellingen](/DeployEdge/microsoft-edge-policies#smartscreen-settings) expliciet beschikbaar voor Microsoft Defender SmartScreen, waaronder een voor het blokkeren [van PUA.](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled) Daarnaast kunnen beheerders [Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) als geheel configureren met groepsbeleidsinstellingen om Microsoft Defender SmartScreen in of uit te schakelen.

Hoewel Microsoft Defender voor Eindpunt een eigen blokkering heeft op basis van een gegevensset die door Microsoft wordt beheerd, kunt u deze lijst aanpassen op basis van uw eigen bedreigingsinformatie. Als u [indicatoren maakt en beheert](manage-indicators.md) in de Microsoft Defender voor Eindpunt-portal, respecteert Microsoft Defender SmartScreen de nieuwe instellingen.

## <a name="microsoft-defender-antivirus-and-pua-protection"></a>Microsoft Defender Antivirus- en PUA-beveiliging

De potentieel ongewenste beveiligingsfunctie voor toepassingen (PUA) in Microsoft Defender Antivirus kan PUA detecteren en blokkeren op eindpunten in uw netwerk.

> [!NOTE]
> Deze functie is beschikbaar in Windows 10, Windows Server 2019 en Windows Server 2016.

Microsoft Defender Antivirus blokkeert gedetecteerde PUA-bestanden en eventuele pogingen om ze te downloaden, te verplaatsen, uit te voeren of te installeren. Geblokkeerde PUA-bestanden worden vervolgens verplaatst naar quarantaine. Wanneer een PUA-bestand wordt gedetecteerd op een eindpunt, stuurt Microsoft Defender Antivirus een melding naar de gebruiker[(tenzij](configure-notifications-microsoft-defender-antivirus.md)meldingen zijn uitgeschakeld) in dezelfde indeling als andere detecties van bedreigingen. De melding wordt vooraf geprefaced met `PUA:` om de inhoud aan te geven.

De melding wordt weergegeven in de gebruikelijke [quarantainelijst in de Windows Security-app.](microsoft-defender-security-center-antivirus.md)

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>PUA-beveiliging configureren in Microsoft Defender Antivirus

U kunt PUA-beveiliging inschakelen [met Microsoft Intune,](/mem/intune/protect/device-protect) [Microsoft Endpoint Configuration Manager,](/mem/configmgr/protect/deploy-use/endpoint-protection) [Groepsbeleid](/azure/active-directory-domain-services/manage-group-policy)of via [PowerShell-cmdlets.](/powershell/module/defender/?preserve-view=true&view=win10-ps)

U kunt ook PUA-beveiliging gebruiken in de auditmodus om potentieel ongewenste toepassingen te detecteren zonder ze te blokkeren. De detecties worden vastgelegd in het Windows-gebeurtenislogboek.

> [!TIP]
> Ga naar de demowebsite van Microsoft Defender voor Eindpunt demo.wd.microsoft.com [om](https://demo.wd.microsoft.com/Page/UrlRep) te bevestigen dat de functie werkt en bekijk deze in actie.

PUA-beveiliging in de auditmodus is handig als uw bedrijf een interne controle van de softwarebeveiliging voert en u eventuele fout-positieven wilt voorkomen.

### <a name="use-intune-to-configure-pua-protection"></a>Intune gebruiken om PUA-beveiliging te configureren

Zie [Instellingen voor apparaatbeperkingen configureren in Microsoft Intune](/intune/device-restrictions-configure) en Microsoft Defender Antivirus apparaatbeperkingen voor [Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) voor meer informatie.

### <a name="use-configuration-manager-to-configure-pua-protection"></a>Configuration Manager gebruiken om PUA-beveiliging te configureren

PUA-beveiliging is standaard ingeschakeld in Microsoft Endpoint Manager (Current Branch).

Zie [Antimalware-beleid](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) maken en implementeren: Instellingen voor geplande scans voor meer informatie over het configureren van Microsoft Endpoint Manager (Current Branch).

Voor System Center 2012 Configuration Manager, zie How to Deploy potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager (Systeemcentrum 2012 Configuration Manager) voor Het implementeren van mogelijk ongewenste toepassingsbeveiligingsbeleid [voor endpointbeveiliging in Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)

> [!NOTE]
> PUA-gebeurtenissen die zijn geblokkeerd door Microsoft Defender Antivirus, worden gerapporteerd in de Windows Event Viewer en niet in Microsoft Endpoint Configuration Manager.

### <a name="use-group-policy-to-configure-pua-protection"></a>Groepsbeleid gebruiken om PUA-beveiliging te configureren

1. Beheersjablonen [(.admx) downloaden en installeren voor Windows 10 oktober 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)

2. Open op uw computer voor groepsbeleidsbeheer de [console Groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

3. Selecteer het groepsbeleidsobject dat u wilt configureren en kies vervolgens **Bewerken.**

4. Ga in **de Groepsbeleidseditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen.**

5. Vouw de boom uit **naar Windows Components** Microsoft Defender  >  **Antivirus**.

6. Dubbelklik op **Detectie configureren voor mogelijk ongewenste toepassingen.**

7. Selecteer **Ingeschakeld om** PUA-beveiliging in te stellen.

8. Selecteer **in** Opties **Blokkeren om** mogelijk ongewenste toepassingen te blokkeren of selecteer **Auditmodus** om te testen hoe de instelling werkt in uw omgeving. Selecteer **OK**.

9. Implementeer het groepsbeleidsobject zoals u gewoonlijk doet.

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>PowerShell-cmdlets gebruiken om PUA-beveiliging te configureren

#### <a name="to-enable-pua-protection"></a>PUA-beveiliging inschakelen

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

Als u de waarde voor deze cmdlet in wilt stellen, schakelt u de `Enabled` functie in als deze is uitgeschakeld.

#### <a name="to-set-pua-protection-to-audit-mode"></a>Pua-beveiliging instellen op auditmodus

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

Met `AuditMode` instelling worden PUA's gedetecteerd zonder ze te blokkeren.

#### <a name="to-disable-pua-protection"></a>PUA-beveiliging uitschakelen

We raden u aan om PUA-beveiliging ingeschakeld te houden. U kunt deze echter uitschakelen met de volgende cmdlet:

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

Als u de waarde voor deze cmdlet instelt, wordt de functie uitgeschakeld `Disabled` als deze is ingeschakeld.

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/index)te configureren en uit te voeren voor meer informatie.

## <a name="view-pua-events-using-powershell"></a>PUA-gebeurtenissen weergeven met PowerShell

PUA-gebeurtenissen worden gerapporteerd in de Windows Event Viewer, maar niet in Microsoft Endpoint Manager of in Intune. U kunt de `Get-MpThreat` cmdlet ook gebruiken om bedreigingen te bekijken die door Microsoft Defender Antivirus zijn afgehandeld. Hier is een voorbeeld:

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

## <a name="get-email-notifications-about-pua-detections"></a>E-mailmeldingen over PUA-detecties ontvangen

U kunt e-mailmeldingen in- en uit- of in- of uit- zetten om e-mail over PUA-detecties te ontvangen.

Zie [Problemen met gebeurtenis-ID's oplossen](troubleshoot-microsoft-defender-antivirus.md) voor meer informatie over het bekijken van Microsoft Defender Antivirus-gebeurtenissen. PUA-gebeurtenissen worden opgenomen onder **gebeurtenis-id 1160**.

## <a name="view-pua-events-using-advanced-hunting"></a>PUA-gebeurtenissen bekijken met behulp van geavanceerde jacht

Als u Microsoft Defender voor [eindpunt](microsoft-defender-endpoint.md)gebruikt, kunt u een geavanceerde query gebruiken om PUA-gebeurtenissen weer te geven. Hier is een voorbeeldquery:

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

Zie Proactief op bedreigingen zoeken met geavanceerde jacht voor meer informatie over geavanceerde [jacht.](advanced-hunting-overview.md)

## <a name="exclude-files-from-pua-protection"></a>Bestanden uitsluiten van PUA-beveiliging

Soms wordt een bestand ten onrechte geblokkeerd door PUA-beveiliging of is een functie van een PUA vereist om een taak te voltooien. In deze gevallen kan een bestand worden toegevoegd aan een uitsluitingslijst.

Zie Uitsluitingen [configureren en valideren op basis van bestandsextensie en maplocatie voor meer informatie.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

## <a name="see-also"></a>Zie ook

- [Beveiliging van de volgende generatie](microsoft-defender-antivirus-in-windows-10.md)
- [Gedrag, heuristiek en realtime bescherming configureren](configure-protection-features-microsoft-defender-antivirus.md)