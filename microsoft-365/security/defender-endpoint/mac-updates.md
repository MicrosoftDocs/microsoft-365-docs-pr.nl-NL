---
title: Updates implementeren voor Microsoft Defender ATP voor Mac
description: Updates voor Microsoft Defender ATP voor Mac beheren in bedrijfsomgevingen.
keywords: microsoft, defender, atp, mac, updates, deploy
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3321c1bd181b89c53e2618fc20fa7f733a20cfc1
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689051"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a>Updates voor Microsoft Defender voor Eindpunt implementeren in macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt op macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft publiceert regelmatig software-updates om de prestaties, beveiliging en nieuwe functies te verbeteren.

Als u Microsoft Defender voor Eindpunt wilt bijwerken op macOS, wordt een programma met de naam Microsoft AutoUpdate (MAU) gebruikt. Mau controleert standaard automatisch dagelijks op updates, maar u kunt dit wijzigen in wekelijks, maandelijks of handmatig.

![MAU-schermafbeelding](images/MDATP-34-MAU.png)

Als u besluit updates te implementeren met behulp van uw softwaredistributieprogramma's, moet u MAU configureren om handmatig te controleren op software-updates. U kunt voorkeuren implementeren om te configureren hoe en wanneer MAU controleert op updates voor de Macs in uw organisatie.

## <a name="use-msupdate"></a>Msupdate gebruiken

MAU bevat een opdrachtregelhulpmiddel, *msupdate* genoemd, dat is ontworpen voor IT-beheerders, zodat ze nauwkeuriger kunnen bepalen wanneer updates worden toegepast. Instructies voor het gebruik van dit hulpprogramma vindt u in [Office voor Mac bijwerken met msupdate.](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)

In MAU is de toepassingsaanduiding voor Microsoft Defender voor Eindpunt op macOS *WDAV00.* Als u de nieuwste updates voor Microsoft Defender voor Eindpunt voor macOS wilt downloaden en installeren, voert u de volgende opdracht uit vanuit een terminalvenster:

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a>Voorkeuren instellen voor Microsoft AutoUpdate

In deze sectie worden de meest voorkomende voorkeuren beschreven die kunnen worden gebruikt om MAU te configureren. Deze instellingen kunnen als configuratieprofiel worden geïmplementeerd via de beheerconsole die uw bedrijf gebruikt. Een voorbeeld van een configuratieprofiel wordt weergegeven in de volgende secties.

### <a name="set-the-channel-name"></a>De kanaalnaam instellen

Het kanaal bepaalt het type en de frequentie van updates die worden aangeboden via MAU. Apparaten in `Beta` kunnen nieuwe functies uitproberen voordat apparaten in en `Preview` `Current` . 

Het `Current` kanaal bevat de meest stabiele versie van het product.

>[!IMPORTANT]
> Voorafgaand aan Microsoft AutoUpdate versie 4.29 hadden kanalen verschillende namen: 
> 
> - `Beta` is benoemd `InsiderFast` (Insider Fast)
> - `Preview` is benoemd `External` (Insider Slow)
> - `Current` is benoemd `Production`

>[!TIP]
>Als u een voorbeeld van nieuwe functies wilt bekijken en vroegtijdig feedback wilt geven, wordt u aangeraden bepaalde apparaten in uw bedrijf te configureren op `Beta` of `Preview` .

|Sectie|Waarde|
|:--|:--|
| **Domein** | com.microsoft.autoupdate2 |
| **Sleutel** | Kanaalnaam |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | Beta <br/> Voorbeeld <br/> Huidige |
|||

>[!WARNING]
>Met deze instelling wordt het kanaal gewijzigd voor alle toepassingen die worden bijgewerkt via Microsoft AutoUpdate. Als u het kanaal alleen wilt wijzigen voor Microsoft Defender voor Eindpunt in macOS, voert u de volgende opdracht uit nadat u het kanaal hebt vervangen door `[channel-name]` het gewenste kanaal:
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a>Updatecontrolefrequentie instellen

Wijzig hoe vaak MAU naar updates zoekt.

|Sectie|Waarde|
|:--|:--|
| **Domein** | com.microsoft.autoupdate2 |
| **Sleutel** | UpdateCheckFrequency |
| **Gegevenstype** | Geheel getal |
| **Standaardwaarde** | 720 (minuten) |
| **Opmerking** | Deze waarde wordt in minuten ingesteld. |


### <a name="change-how-mau-interacts-with-updates"></a>De interactie tussen MAU en updates wijzigen

Wijzig de manier waarop MAU zoekt naar updates.

|Sectie|Waarde|
|:--|:--|
| **Domein** | com.microsoft.autoupdate2 |
| **Sleutel** | HowToCheck |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | Handmatig <br/> Automatisch controleren <br/> AutomaticDownload |
| **Opmerking** |  Houd er rekening mee dat AutomaticDownload indien mogelijk wordt gedownload en geruisloos wordt geïnstalleerd. |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a>Wijzigen of de knop Controleren op updates is ingeschakeld

Wijzig of lokale gebruikers kunnen klikken op de optie Controleren op updates in de gebruikersinterface van Microsoft AutoUpdate.

|Sectie|Waarde|
|:--|:--|
| **Domein** | com.microsoft.autoupdate2 |
| **Sleutel** | EnableCheckForUpdatesButton |
| **Gegevenstype** | Booleaanse waarde |
| **Mogelijke waarden** | Waar (standaard) <br/> Onwaar |


### <a name="disable-insider-checkbox"></a>Selectievakje Insider uitschakelen

Ingesteld op waar om het 'Deelnemen aan het Office Insider-programma' te maken... selectievakje niet beschikbaar / grijs voor gebruikers.

|Sectie|Waarde|
|:--|:--|
| **Domein** | com.microsoft.autoupdate2 |
| **Sleutel** | DisableInsiderCheckbox |
| **Gegevenstype** | Booleaanse waarde |
| **Mogelijke waarden** | Onwaar (standaard) <br/> Waar |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a>De telemetrie beperken die wordt verzonden vanuit MAU

Instellen op onwaar om minimale heartbeatgegevens te verzenden, geen toepassingsgebruik en geen omgevingsgegevens.

|Sectie|Waarde|
|:--|:--|
| **Domein** | com.microsoft.autoupdate2 |
| **Sleutel** | SendAllTelemetryEnabled |
| **Gegevenstype** | Booleaanse waarde |
| **Mogelijke waarden** | Waar (standaard) <br/> Onwaar |


## <a name="example-configuration-profile"></a>Voorbeeld van configuratieprofiel

Het volgende configuratieprofiel wordt gebruikt om:
- Het apparaat in het bètakanaal plaatsen
- Updates automatisch downloaden en installeren
- De knop Controleren op updates inschakelen in de gebruikersinterface
- Gebruikers op het apparaat toestaan zich aan te melden bij de Insider-kanalen

### <a name="jamf"></a>JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Beta</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a>Intune

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Beta</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

Als u MAU wilt configureren, kunt u dit configuratieprofiel implementeren vanuit het beheerprogramma dat uw bedrijf gebruikt:
- Upload dit configuratieprofiel vanuit JAMF en stel het voorkeursdomein in *op com.microsoft.autoupdate2.*
- Upload dit configuratieprofiel vanuit Intune en stel de naam van het aangepaste configuratieprofiel in *op com.microsoft.autoupdate2.*

## <a name="resources"></a>Resources

- [msupdate-verwijzing](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
