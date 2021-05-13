---
title: Voorkeuren instellen voor Microsoft Defender voor Eindpunt op Mac
description: Configureer MMicrosoft Defender voor Endpoint op Mac in bedrijfsorganisaties.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, management, preferences, enterprise, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: b706cb8dbd43d545768c1c573021b5ef401e3c09
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346400"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a>Voorkeuren instellen voor Microsoft Defender voor Eindpunt op macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt op macOS](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
>Dit artikel bevat instructies voor het instellen van voorkeuren voor Microsoft Defender voor Eindpunt voor macOS in bedrijfsorganisaties. Zie Resources als u Microsoft Defender voor Eindpunt op [](mac-resources.md#configuring-from-the-command-line)macOS wilt configureren met behulp van de opdrachtregelinterface.

## <a name="summary"></a>Samenvatting

In ondernemingsorganisaties kan Microsoft Defender voor Eindpunt op macOS worden beheerd via een configuratieprofiel dat wordt geïmplementeerd met behulp van een van de verschillende beheerhulpmiddelen. Voorkeuren die worden beheerd door uw beveiligingsbewerkingsteam, hebben voorrang op voorkeuren die lokaal op het apparaat zijn ingesteld. Het wijzigen van de voorkeuren die zijn ingesteld via het configuratieprofiel vereist geëscaleerde bevoegdheden en is niet beschikbaar voor gebruikers zonder beheerdersmachtigingen.

In dit artikel wordt de structuur van het configuratieprofiel beschreven, wordt een aanbevolen profiel beschreven dat u kunt gebruiken om aan de slag te gaan en worden instructies gegeven over het implementeren van het profiel.

## <a name="configuration-profile-structure"></a>Configuratieprofielstructuur

Het configuratieprofiel is een *PLIST-bestand* dat bestaat uit items die zijn geïdentificeerd met een sleutel (die de naam van de voorkeur aan duidt), gevolgd door een waarde, die afhankelijk is van de aard van de voorkeur. Waarden kunnen eenvoudig zijn (zoals een numerieke waarde) of complex, zoals een geneste lijst met voorkeuren.

>[!CAUTION]
>De indeling van het configuratieprofiel is afhankelijk van de beheerconsole die u gebruikt. De volgende secties bevatten voorbeelden van configuratieprofielen voor JAMF en Intune.

Het bovenste niveau van het configuratieprofiel bevat productvoorkeuren en vermeldingen voor subareas van Microsoft Defender voor Eindpunt, die in de volgende secties in meer detail worden beschreven.

### <a name="antivirus-engine-preferences"></a>Voorkeuren voor antivirusprogramma's

De *antivirusEngine-sectie* van het configuratieprofiel wordt gebruikt om de voorkeuren van het antivirusonderdeel van Microsoft Defender voor Eindpunt te beheren.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | antivirusEngine |
| **Gegevenstype** | Woordenlijst (geneste voorkeur) |
| **Opmerkingen** | Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst. |

#### <a name="enable--disable-real-time-protection"></a>Realtime beveiliging in- of uitschakelen

Geef op of u realtimebeveiliging wilt inschakelen, waarmee bestanden worden gescand wanneer ze worden toegankelijk.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | enableRealTimeProtection |
| **Gegevenstype** | Booleaanse waarde |
| **Mogelijke waarden** | true (standaard) <br/> onwaar |

#### <a name="enable--disable-passive-mode"></a>Passieve modus in- of uitschakelen

Geef op of de antivirusprogramma's in de passieve modus worden uitgevoerd. De passieve modus heeft de volgende gevolgen: 
- Realtimebeveiliging is uitgeschakeld
- Scannen op aanvraag is ingeschakeld
- Automatische herstel van bedreigingen is uitgeschakeld
- Beveiligingsinformatie-updates zijn ingeschakeld
- Pictogram statusmenu is verborgen

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | passiveMode |
| **Gegevenstype** | Booleaanse waarde |
| **Mogelijke waarden** | onwaar (standaard) <br/> waar |
| **Opmerkingen** | Beschikbaar in Microsoft Defender voor Eindpunt versie 100.67.60 of hoger. |

#### <a name="exclusion-merge-policy"></a>Beleid voor samenvoeging van uitsluiting

Geef het samenvoegbeleid op voor uitsluitingen. Dit kan een combinatie zijn van door de beheerder gedefinieerde en door de gebruiker gedefinieerde uitsluitingen ( ) of alleen `merge` door beheerders gedefinieerde uitsluitingen ( `admin_only` ). Deze instelling kan worden gebruikt om te voorkomen dat lokale gebruikers hun eigen uitsluitingen definiëren.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | uitsluitingenMergePolicy |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | samenvoegen (standaard) <br/> admin_only |
| **Opmerkingen** | Beschikbaar in Microsoft Defender voor Eindpunt versie 100.83.73 of hoger. |

#### <a name="scan-exclusions"></a>Uitsluitingen scannen

Geef entiteiten op die niet mogen worden gescand. Uitsluitingen kunnen worden opgegeven door volledige paden, extensies of bestandsnamen.
(Uitsluitingen worden opgegeven als een matrix met items, beheerder kan zo veel elementen opgeven als nodig is, in elke volgorde.)

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | uitsluitingen |
| **Gegevenstype** | Woordenlijst (geneste voorkeur) |
| **Opmerkingen** | Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst. |

##### <a name="type-of-exclusion"></a>Type uitsluiting

Geef inhoud op die niet per type kan worden gescand.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | $type |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | excludedPath <br/> uitgeslotenFileExtension <br/> uitgeslotenFileName |

##### <a name="path-to-excluded-content"></a>Pad naar uitgesloten inhoud

Geef inhoud op die niet kan worden gescand via een volledig bestandspad.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | pad |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | geldige paden |
| **Opmerkingen** | Alleen van toepassing *als $type* *is uitgeslotenPath* |

## <a name="supported-exclusion-types"></a>Ondersteunde uitsluitingstypen

In de volgende tabel ziet u de uitsluitingstypen die worden ondersteund door Defender voor Eindpunt op Mac.

Uitsluiting | Definitie | Voorbeelden
---|---|---
Bestandsextensie | Alle bestanden met de extensie, overal op het apparaat | `.test`
Bestand | Een specifiek bestand dat is geïdentificeerd door het volledige pad | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
Map | Alle bestanden onder de opgegeven map (recursief) | `/var/log/`<br/>`/var/*/`
Proces | Een specifiek proces (opgegeven door het volledige pad of de bestandsnaam) en alle bestanden die hiermee worden geopend | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> De bovenstaande paden moeten harde koppelingen zijn, geen symbolische koppelingen, om te kunnen worden uitgesloten. U kunt controleren of een pad een symbolische koppeling is door te `file <path-name>` lopen.

Bestands-, map- en procesuitsluitingen ondersteunen de volgende jokertekens:

Jokerteken | Omschrijving | Voorbeeld | Overeenkomsten | Komt niet overeen met
---|---|---|---|---
\* |    Komt overeen met een aantal tekens, inclusief geen tekens (houd er rekening mee dat wanneer dit jokerteken binnen een pad wordt gebruikt, dit slechts één map vervangt) | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
? | Komt overeen met een enkel teken | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

##### <a name="path-type-file--directory"></a>Padtype (bestand /adreslijst)

Geef aan of *de eigenschap pad* verwijst naar een bestand of adreslijst. 

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | isDirectory |
| **Gegevenstype** | Booleaanse waarde |
| **Mogelijke waarden** | onwaar (standaard) <br/> waar |
| **Opmerkingen** | Alleen van toepassing *als $type* *is uitgeslotenPath* |

##### <a name="file-extension-excluded-from-the-scan"></a>Bestandsextensie uitgesloten van de scan

Geef inhoud op die niet kan worden gescand door bestandsextensie.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | extensie |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | geldige bestandsextensies |
| **Opmerkingen** | Alleen van toepassing *als $type* *is uitgeslotenFileExtension* |

##### <a name="process-excluded-from-the-scan"></a>Proces uitgesloten van de scan

Geef een proces op waarvoor alle bestandsactiviteit is uitgesloten van scannen. Het proces kan worden opgegeven door de naam (bijvoorbeeld) of het volledige `cat` pad `/bin/cat` (bijvoorbeeld).

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | naam |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | een tekenreeks |
| **Opmerkingen** | Alleen van toepassing *als $type* *is uitgeslotenFileName* |

#### <a name="allowed-threats"></a>Toegestane bedreigingen

Geef bedreigingen op op naam die niet worden geblokkeerd door Defender voor Eindpunt op Mac. Deze bedreigingen kunnen worden uitgevoerd.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | toegestaanThreats |
| **Gegevenstype** | Matrix met tekenreeksen |

#### <a name="disallowed-threat-actions"></a>Niet-toegestaan bedreigingsacties

Hiermee beperkt u de acties die de lokale gebruiker van een apparaat kan uitvoeren wanneer bedreigingen worden gedetecteerd. De acties in deze lijst worden niet weergegeven in de gebruikersinterface.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | disallowedThreatActions |
| **Gegevenstype** | Matrix met tekenreeksen |
| **Mogelijke waarden** | toestaan (gebruikers kunnen geen bedreigingen toestaan) <br/> herstellen (gebruikers kunnen geen bedreigingen herstellen vanuit de quarantaine) |
| **Opmerkingen** | Beschikbaar in Microsoft Defender voor Eindpunt versie 100.83.73 of hoger. |

#### <a name="threat-type-settings"></a>Instellingen voor bedreigingstype

Geef op hoe bepaalde bedreigingstypen worden verwerkt door Microsoft Defender voor Eindpunt in macOS.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | threatTypeSettings |
| **Gegevenstype** | Woordenlijst (geneste voorkeur) |
| **Opmerkingen** | Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst. |

##### <a name="threat-type"></a>Type bedreiging

Geef bedreigingstypen op.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | toets |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | potentially_unwanted_application <br/> archive_bomb |

##### <a name="action-to-take"></a>Actie ondernemen

Geef op welke actie moet worden ondernomen wanneer er een bedreiging wordt gedetecteerd van het type dat is opgegeven in de vorige sectie. Kies uit de volgende opties:

- **Audit:** uw apparaat is niet beveiligd tegen dit type bedreiging, maar er wordt wel een vermelding over de bedreiging geregistreerd.
- **Blokkeren:** uw apparaat is beveiligd tegen dit type bedreiging en u krijgt een melding in de gebruikersinterface en de beveiligingsconsole.
- **Uit:** uw apparaat is niet beveiligd tegen dit type bedreiging en er wordt niets geregistreerd.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | waarde |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | audit (standaard) <br/> blokkering <br/> uit |

#### <a name="threat-type-settings-merge-policy"></a>Samenvoegbeleid voor instellingen voor bedreigingstype

Geef het samenvoegbeleid op voor instellingen voor bedreigingstype. Dit kan een combinatie zijn van door de beheerder gedefinieerde en door de gebruiker gedefinieerde instellingen ( `merge` ) of alleen door beheerders gedefinieerde instellingen ( `admin_only` ). Deze instelling kan worden gebruikt om te voorkomen dat lokale gebruikers hun eigen instellingen voor verschillende bedreigingstypen definiëren.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | threatTypeSettingsMergePolicy |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | samenvoegen (standaard) <br/> admin_only |
| **Opmerkingen** | Beschikbaar in Microsoft Defender voor Eindpunt versie 100.83.73 of hoger. |

#### <a name="antivirus-scan-history-retention-in-days"></a>Bewaargeschiedenis van antivirusscans (in dagen)

Geef het aantal dagen op dat de resultaten worden bewaard in de scangeschiedenis op het apparaat. Oude scanresultaten worden uit de geschiedenis verwijderd. Oude in quarantaine geplaatste bestanden die ook van de schijf zijn verwijderd.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | scanResultsRetentionDays |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | 90 (standaard). Toegestane waarden zijn 1 dag tot 180 dagen. |
| **Opmerkingen** | Beschikbaar in Microsoft Defender voor Eindpunt versie 101.07.23 of hoger. |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>Maximum aantal items in de geschiedenis van de antivirusscan

Geef het maximum aantal items op dat u wilt behouden in de scangeschiedenis. Items zijn alle scans op aanvraag die in het verleden zijn uitgevoerd en alle antivirusdetecties.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | scanHistoryMaximumItems |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | 10000 (standaard). Toegestane waarden zijn van 5000 items tot 15000 items. |
| **Opmerkingen** | Beschikbaar in Microsoft Defender voor Eindpunt versie 101.07.23 of hoger. |

### <a name="cloud-delivered-protection-preferences"></a>Beveiligingsvoorkeuren in de cloud

Configureer de cloudbeveiligingsfuncties van Microsoft Defender voor Eindpunt op macOS.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | cloudService |
| **Gegevenstype** | Woordenlijst (geneste voorkeur) |
| **Opmerkingen** | Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst. |

#### <a name="enable--disable-cloud-delivered-protection"></a>Beveiliging via de cloud in- of uitschakelen

Geef op of u de beveiliging van het apparaat al dan niet wilt inschakelen in de cloud. Als u de beveiliging van uw services wilt verbeteren, raden we u aan deze functie ingeschakeld te houden.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | ingeschakeld |
| **Gegevenstype** | Booleaanse waarde |
| **Mogelijke waarden** | true (standaard) <br/> onwaar |

#### <a name="diagnostic-collection-level"></a>Diagnostisch verzamelingsniveau

Diagnostische gegevens worden gebruikt om Microsoft Defender voor Eindpunt veilig en up-to-date te houden, problemen op te sporen, te diagnosticeren en op te lossen, en om productverbeteringen aan te brengen. Deze instelling bepaalt het niveau van de diagnostische gegevens die door Microsoft Defender voor Eindpunt naar Microsoft worden verzonden.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | diagnosticLevel |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | optioneel (standaard) <br/> Vereist |

#### <a name="enable--disable-automatic-sample-submissions"></a>Automatische voorbeeldinzendingen in- of uitschakelen

Hiermee wordt bepaald of verdachte steekproeven (die waarschijnlijk bedreigingen bevatten) naar Microsoft worden verzonden. U wordt gevraagd of het ingediende bestand waarschijnlijk persoonlijke gegevens bevat.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | automaticSampleSubmission |
| **Gegevenstype** | Booleaanse waarde |
| **Mogelijke waarden** | true (standaard) <br/> onwaar |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>Automatische beveiligingsinformatie-updates in- of uitschakelen

Hiermee bepaalt u of beveiligingsinformatieupdates automatisch worden geïnstalleerd:

|Sectie|Waarde|
|:---|:---|
| **Sleutel** | automaticDefinitionUpdateEnabled |
| **Gegevenstype** | Booleaanse waarde |
| **Mogelijke waarden** | true (standaard) <br/> onwaar |

### <a name="user-interface-preferences"></a>Gebruikersinterfacevoorkeuren

Beheer de voorkeuren voor de gebruikersinterface van Microsoft Defender voor Eindpunt op macOS.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | userInterface |
| **Gegevenstype** | Woordenlijst (geneste voorkeur) |
| **Opmerkingen** | Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst. |

#### <a name="show--hide-status-menu-icon"></a>Pictogram statusmenu weergeven/verbergen

Geef op of u het statusmenupictogram wilt weergeven of verbergen in de rechterbovenhoek van het scherm.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | StatusMenuIcon verbergen |
| **Gegevenstype** | Booleaanse waarde |
| **Mogelijke waarden** | onwaar (standaard) <br/> waar |

#### <a name="show--hide-option-to-send-feedback"></a>Optie weergeven/verbergen om feedback te verzenden

Geef op of gebruikers feedback kunnen verzenden naar Microsoft door naar `Help`  >  `Send Feedback` .

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | userInitiatedFeedback |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | ingeschakeld (standaard) <br/> uitgeschakeld |
| **Opmerkingen** | Beschikbaar in Microsoft Defender voor Eindpunt versie 101.19.61 of hoger. |

### <a name="endpoint-detection-and-response-preferences"></a>Eindpuntdetectie- en antwoordvoorkeuren

Beheer de voorkeuren van het eindpuntdetectie en -respons (EDR) van Microsoft Defender voor Eindpunt in macOS.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | edr |
| **Gegevenstype** | Woordenlijst (geneste voorkeur) |
| **Opmerkingen** | Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst. |

#### <a name="device-tags"></a>Apparaatlabels

Geef een tagnaam en de waarde op. 

- Met de tag GROEP wordt het apparaat gelabeld met de opgegeven waarde. De tag wordt weergegeven in de portal onder de apparaatpagina en kan worden gebruikt voor het filteren en groeperen van apparaten.

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | tags |
| **Gegevenstype** | Woordenlijst (geneste voorkeur) |
| **Opmerkingen** | Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst. |

##### <a name="type-of-tag"></a>Type tag

Geeft het type tag op

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | toets |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | `GROUP` |

##### <a name="value-of-tag"></a>Waarde van tag

Geeft de waarde van de tag op

|Sectie|Waarde|
|:---|:---|
| **Domein** | `com.microsoft.wdav` |
| **Sleutel** | waarde |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | een tekenreeks |

> [!IMPORTANT]  
> - Er kan slechts één waarde per tagtype worden ingesteld.
> - Het type tags is uniek en mag niet worden herhaald in hetzelfde configuratieprofiel.

## <a name="recommended-configuration-profile"></a>Aanbevolen configuratieprofiel

Om aan de slag te gaan, wordt u aangeraden de volgende configuratie voor uw bedrijf te gebruiken om te profiteren van alle beveiligingsfuncties die Microsoft Defender voor Eindpunt biedt.

Het volgende configuratieprofiel (of, in het geval van JAMF, een eigenschappenlijst die kan worden geüpload naar het configuratieprofiel voor aangepaste instellingen) wordt als volgt weergegeven:
- Realtimebeveiliging inschakelen (RTP)
- Geef op hoe de volgende bedreigingstypen worden verwerkt:
  - **Potentieel ongewenste toepassingen (PUA)** worden geblokkeerd
  - **Archiefbommen** (bestand met een hoge compressiesnelheid) worden gecontroleerd op Microsoft Defender voor eindpuntlogboeken
- Automatische beveiligingsinformatie-updates inschakelen
- Cloudbeveiliging inschakelen
- Automatische voorbeeldinzending inschakelen

### <a name="property-list-for-jamf-configuration-profile"></a>Eigenschappenlijst voor HET CONFIGURATIEprofiel VAN JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a>Intune-profiel

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
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
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a>Voorbeeld van volledig configuratieprofiel

De volgende sjablonen bevatten vermeldingen voor alle instellingen die in dit document worden beschreven en kunnen worden gebruikt voor meer geavanceerde scenario's waarin u meer controle wilt over Microsoft Defender voor Eindpunt in macOS.

### <a name="property-list-for-jamf-configuration-profile"></a>Eigenschappenlijst voor HET CONFIGURATIEprofiel VAN JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/Users/*/git</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a>Intune-profiel

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
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
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/Users/*/git</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a>Validatie van eigenschappenlijst

De lijst met eigenschappen moet een geldig *PLIST-bestand* zijn. U kunt dit controleren door het volgende uit te voeren:

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

Als het bestand goed is gevormd, wordt met de bovenstaande opdracht een exitcode van `OK` `0` . Anders wordt een fout weergegeven die het probleem beschrijft en retourneert de opdracht een exitcode van `1` .

## <a name="configuration-profile-deployment"></a>Implementatie van configuratieprofiel

Nadat u het configuratieprofiel voor uw bedrijf hebt gemaakt, kunt u het implementeren via de beheerconsole die uw bedrijf gebruikt. In de volgende secties worden instructies gegeven voor het implementeren van dit profiel met BEHULP van JAMF en Intune.

### <a name="jamf-deployment"></a>JAMF-implementatie

Open in de JAMF-console **De configuratieprofielen** van computers, navigeer naar het configuratieprofiel dat u wilt gebruiken en selecteer vervolgens  >   **Aangepaste Instellingen.** Maak een item met `com.microsoft.wdav` als voorkeursdomein en upload de *.plist die* eerder is gemaakt.

>[!CAUTION]
>U moet het juiste voorkeursdomein invoeren ( ); anders worden de voorkeuren niet herkend `com.microsoft.wdav` door Microsoft Defender voor Eindpunt.

### <a name="intune-deployment"></a>Intune-implementatie

1. Open   >  **Apparaatconfiguratie beheren.** Selecteer **Profielen beheren**  >  **Profiel**  >  **maken.**

2. Kies een naam voor het profiel. **Platform=macOS wijzigen** in **Profieltype=Aangepast**. Selecteer Configureren.

3. Sla de eerder geproduceerde PLIST op als `com.microsoft.wdav.xml` .

4. Voer `com.microsoft.wdav` de naam van het aangepaste **configuratieprofiel in.**

5. Open het configuratieprofiel en upload het `com.microsoft.wdav.xml` bestand. (Dit bestand is gemaakt in stap 3.)

6. Kies **OK**.

7. Selecteer **Opdrachten**  >  **beheren.** Selecteer op **het** tabblad Opnemen de optie Toewijzen aan **alle & alle apparaten.**

>[!CAUTION]
>U moet de juiste naam van het aangepaste configuratieprofiel invoeren. Anders worden deze voorkeuren niet herkend door Microsoft Defender voor Eindpunt.

## <a name="resources"></a>Resources

- [Documentatie over configuratieprofielen (documentatie van Apple voor ontwikkelaars, Engelstalig)](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
