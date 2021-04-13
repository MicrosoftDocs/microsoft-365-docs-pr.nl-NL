---
title: Voorkeuren instellen voor Microsoft Defender ATP voor Linux
ms.reviewer: ''
description: Hier wordt beschreven hoe u Microsoft Defender ATP configureert voor Linux in ondernemingen.
keywords: microsoft, defender, atp, linux, installatie, implementeren, verwijderen, pop, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6ca6b3dd41b867145bfc4af331fb742be469d2a9
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688391"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a>Voorkeuren instellen voor Microsoft Defender voor Eindpunt op Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
>Dit onderwerp bevat instructies voor het instellen van voorkeuren voor Defender voor Eindpunt voor Linux in bedrijfsomgevingen. Zie Resources als u geïnteresseerd bent in het configureren [](linux-resources.md#configure-from-the-command-line)van het product op een apparaat vanaf de opdrachtregel.

In bedrijfsomgevingen kan Defender voor Endpoint voor Linux worden beheerd via een configuratieprofiel. Dit profiel wordt geïmplementeerd vanuit het beheerprogramma van uw keuze. Voorkeuren die door de onderneming worden beheerd, hebben voorrang op de voorkeuren die lokaal op het apparaat zijn ingesteld. Met andere woorden: gebruikers in uw bedrijf kunnen geen voorkeuren wijzigen die zijn ingesteld via dit configuratieprofiel.

In dit artikel wordt de structuur van dit profiel beschreven (inclusief een aanbevolen profiel dat u kunt gebruiken om aan de slag te gaan) en instructies voor het implementeren van het profiel.

## <a name="configuration-profile-structure"></a>Configuratieprofielstructuur

Het configuratieprofiel is een JSON-bestand dat bestaat uit items die zijn geïdentificeerd met een sleutel (die de naam van de voorkeur aan duidt), gevolgd door een waarde, die afhankelijk is van de aard van de voorkeur. Waarden kunnen eenvoudig zijn, zoals een numerieke waarde of complex, zoals een geneste lijst met voorkeuren.

Meestal gebruikt u een configuratiebeheerprogramma om een bestand met de naam op de ```mdatp_managed.json``` locatie te ```/etc/opt/microsoft/mdatp/managed/``` pushen.

Het bovenste niveau van het configuratieprofiel bevat productvoorkeuren en vermeldingen voor subareas van het product, die in de volgende secties in meer detail worden beschreven.

### <a name="antivirus-engine-preferences"></a>Voorkeuren voor antivirusprogramma's

De *antivirusEngine-sectie* van het configuratieprofiel wordt gebruikt om de voorkeuren van het antivirusonderdeel van het product te beheren.

|||
|:---|:---|
| **Sleutel** | antivirusEngine |
| **Gegevenstype** | Woordenlijst (geneste voorkeur) |
| **Opmerkingen** | Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst. |
|||

#### <a name="enable--disable-real-time-protection"></a>Realtime beveiliging in- of uitschakelen

Hiermee bepaalt u of realtimebeveiliging (bestanden scannen terwijl ze worden toegankelijk) is ingeschakeld of niet.

|||
|:---|:---|
| **Sleutel** | enableRealTimeProtection |
| **Gegevenstype** | Booleaanse waarde |
| **Mogelijke waarden** | true (standaard) <br/> onwaar |
|||

#### <a name="enable--disable-passive-mode"></a>Passieve modus in- of uitschakelen

Hiermee bepaalt u of de antivirusprogramma's al dan niet in de passieve modus worden uitgevoerd. In de passieve modus:
- Realtimebeveiliging is uitgeschakeld.
- Scannen op aanvraag is ingeschakeld.
- Automatische herstel van bedreigingen is uitgeschakeld.
- Beveiligingsinformatie-updates zijn ingeschakeld.
- Pictogram statusmenu is verborgen.

|||
|:---|:---|
| **Sleutel** | passiveMode |
| **Gegevenstype** | Booleaanse waarde |
| **Mogelijke waarden** | onwaar (standaard) <br/> waar |
| **Opmerkingen** | Beschikbaar in Defender voor Eindpunt versie 100.67.60 of hoger. |
|||

#### <a name="exclusion-merge-policy"></a>Beleid voor samenvoeging van uitsluiting

Hiermee geeft u het samenvoegbeleid voor uitsluitingen op. Het kan een combinatie zijn van door de beheerder gedefinieerde en door de gebruiker gedefinieerde uitsluitingen ( ) of alleen `merge` door beheerders gedefinieerde uitsluitingen ( `admin_only` ). Deze instelling kan worden gebruikt om te voorkomen dat lokale gebruikers hun eigen uitsluitingen definiëren.

|||
|:---|:---|
| **Sleutel** | uitsluitingenMergePolicy |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | samenvoegen (standaard) <br/> admin_only |
| **Opmerkingen** | Beschikbaar in Defender voor Eindpunt versie 100.83.73 of hoger. |
|||

#### <a name="scan-exclusions"></a>Uitsluitingen scannen

Entiteiten die zijn uitgesloten van de scan. Uitsluitingen kunnen worden opgegeven door volledige paden, extensies of bestandsnamen.

|||
|:---|:---|
| **Sleutel** | uitsluitingen |
| **Gegevenstype** | Woordenlijst (geneste voorkeur) |
| **Opmerkingen** | Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst. |
|||

**Type uitsluiting**

Hiermee geeft u het type inhoud op dat is uitgesloten van de scan.

|||
|:---|:---|
| **Sleutel** | $type |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | excludedPath <br/> uitgeslotenFileExtension <br/> uitgeslotenFileName |
|||

**Pad naar uitgesloten inhoud**

Wordt gebruikt om inhoud op volledig bestandspad uit te sluiten van de scan.

|||
|:---|:---|
| **Sleutel** | pad |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | geldige paden |
| **Opmerkingen** | Alleen van toepassing *als $type* *is uitgeslotenPath* |
|||

**Padtype (bestand /adreslijst)**

Hiermee wordt aangegeven of *de eigenschap pad* verwijst naar een bestand of adreslijst. 

|||
|:---|:---|
| **Sleutel** | isDirectory |
| **Gegevenstype** | Booleaanse waarde |
| **Mogelijke waarden** | onwaar (standaard) <br/> waar |
| **Opmerkingen** | Alleen van toepassing *als $type* *is uitgeslotenPath* |
|||

**Bestandsextensie uitgesloten van de scan**

Wordt gebruikt om inhoud uit te sluiten van de scan via bestandsextensie.

|||
|:---|:---|
| **Sleutel** | extensie |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | geldige bestandsextensies |
| **Opmerkingen** | Alleen van toepassing *als $type* *is uitgeslotenFileExtension* |
|||

**Proces uitgesloten van de scan**

Hiermee geeft u een proces op waarvoor alle bestandsactiviteit niet kan worden gescand. Het proces kan worden opgegeven door de naam (bijvoorbeeld) of het volledige `cat` pad `/bin/cat` (bijvoorbeeld).

|||
|:---|:---|
| **Sleutel** | naam |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | een tekenreeks |
| **Opmerkingen** | Alleen van toepassing *als $type* *is uitgeslotenFileName* |
|||

#### <a name="allowed-threats"></a>Toegestane bedreigingen

Lijst met bedreigingen (geïdentificeerd met hun naam) die niet worden geblokkeerd door het product en die in plaats daarvan mogen worden uitgevoerd.

|||
|:---|:---|
| **Sleutel** | toegestaanThreats |
| **Gegevenstype** | Matrix met tekenreeksen |
|||

#### <a name="disallowed-threat-actions"></a>Niet-toegestaan bedreigingsacties

Hiermee beperkt u de acties die de lokale gebruiker van een apparaat kan uitvoeren wanneer bedreigingen worden gedetecteerd. De acties in deze lijst worden niet weergegeven in de gebruikersinterface.

|||
|:---|:---|
| **Sleutel** | disallowedThreatActions |
| **Gegevenstype** | Matrix met tekenreeksen |
| **Mogelijke waarden** | toestaan (gebruikers kunnen geen bedreigingen toestaan) <br/> herstellen (gebruikers kunnen geen bedreigingen herstellen vanuit de quarantaine) |
| **Opmerkingen** | Beschikbaar in Defender voor Eindpunt versie 100.83.73 of hoger. |
|||

#### <a name="threat-type-settings"></a>Instellingen voor bedreigingstype

De *threatTypeSettings-voorkeur* in de antivirus-engine wordt gebruikt om te bepalen hoe bepaalde bedreigingstypen door het product worden verwerkt.

|||
|:---|:---|
| **Sleutel** | threatTypeSettings |
| **Gegevenstype** | Woordenlijst (geneste voorkeur) |
| **Opmerkingen** | Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst. |
|||

**Type bedreiging**

Type bedreiging waarvoor het gedrag is geconfigureerd.

|||
|:---|:---|
| **Sleutel** | toets |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | potentially_unwanted_application <br/> archive_bomb |
|||

**Actie ondernemen**

Actie die moet worden ondernomen wanneer u een bedreiging tegenkomt van het type dat is opgegeven in de vorige sectie. Kan het volgende zijn:

- **Controle:** Het apparaat is niet beveiligd tegen dit type bedreiging, maar er wordt wel een vermelding over de bedreiging geregistreerd.
- **Blokkeren:** Het apparaat is beveiligd tegen dit type bedreiging en u wordt op de hoogte gesteld in de beveiligingsconsole.
- **Uit:** Het apparaat is niet beveiligd tegen dit type bedreiging en er wordt niets geregistreerd.

|||
|:---|:---|
| **Sleutel** | waarde |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | audit (standaard) <br/> blokkering <br/> uit |
|||

#### <a name="threat-type-settings-merge-policy"></a>Samenvoegbeleid voor instellingen voor bedreigingstype

Hiermee geeft u het samenvoegbeleid voor instellingen voor bedreigingstype op. Dit kan een combinatie zijn van door de beheerder gedefinieerde en door de gebruiker gedefinieerde instellingen ( `merge` ) of alleen door beheerders gedefinieerde instellingen ( `admin_only` ). Deze instelling kan worden gebruikt om te voorkomen dat lokale gebruikers hun eigen instellingen voor verschillende bedreigingstypen definiëren.

|||
|:---|:---|
| **Sleutel** | threatTypeSettingsMergePolicy |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | samenvoegen (standaard) <br/> admin_only |
| **Opmerkingen** | Beschikbaar in Defender voor Eindpunt versie 100.83.73 of hoger. |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a>Bewaargeschiedenis van antivirusscans (in dagen)

Geef het aantal dagen op dat de resultaten worden bewaard in de scangeschiedenis op het apparaat. Oude scanresultaten worden uit de geschiedenis verwijderd. Oude in quarantaine geplaatste bestanden die ook van de schijf zijn verwijderd.

|||
|:---|:---|
| **Sleutel** | scanResultsRetentionDays |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | 90 (standaard). Toegestane waarden zijn 1 dag tot 180 dagen. |
| **Opmerkingen** | Beschikbaar in Defender voor Eindpunt versie 101.04.76 of hoger. |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>Maximum aantal items in de geschiedenis van de antivirusscan

Geef het maximum aantal items op dat u wilt behouden in de scangeschiedenis. Items zijn alle scans op aanvraag die in het verleden zijn uitgevoerd en alle antivirusdetecties.

|||
|:---|:---|
| **Sleutel** | scanHistoryMaximumItems |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | 10000 (standaard). Toegestane waarden zijn van 5000 items tot 15000 items. |
| **Opmerkingen** | Beschikbaar in Defender voor Eindpunt versie 101.04.76 of hoger. |
|||

### <a name="cloud-delivered-protection-preferences"></a>Beveiligingsvoorkeuren in de cloud

De *cloudService-vermelding* in het configuratieprofiel wordt gebruikt om de cloudbeveiligingsfunctie van het product te configureren.

|||
|:---|:---|
| **Sleutel** | cloudService |
| **Gegevenstype** | Woordenlijst (geneste voorkeur) |
| **Opmerkingen** | Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst. |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a>Beveiliging via de cloud in- of uitschakelen

Hiermee bepaalt u of beveiliging in de cloud is ingeschakeld op het apparaat of niet. Als u de beveiliging van uw services wilt verbeteren, raden we u aan deze functie ingeschakeld te houden.

|||
|:---|:---|
| **Sleutel** | ingeschakeld |
| **Gegevenstype** | Booleaanse waarde |
| **Mogelijke waarden** | true (standaard) <br/> onwaar |
|||

#### <a name="diagnostic-collection-level"></a>Diagnostisch verzamelingsniveau

Diagnostische gegevens worden gebruikt om Defender voor Eindpunt veilig en up-to-date te houden, problemen op te sporen, te diagnosticeren en op te lossen, en om productverbeteringen aan te brengen. Deze instelling bepaalt het niveau van de diagnostische gegevens die door het product naar Microsoft worden verzonden.

|||
|:---|:---|
| **Sleutel** | diagnosticLevel |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | optioneel (standaard) <br/> Vereist |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a>Automatische voorbeeldinzendingen in- of uitschakelen

Hiermee wordt bepaald of verdachte steekproeven (die waarschijnlijk bedreigingen bevatten) naar Microsoft worden verzonden. Er zijn drie niveaus voor het beheren van voorbeeldinzending:

- **Geen:** er worden geen verdachte steekproeven ingediend bij Microsoft.
- **Veilig:** alleen verdachte steekproeven die geen persoonlijk identificeerbare gegevens (PII) bevatten, worden automatisch verzonden. Dit is de standaardwaarde voor deze instelling.
- **Alle**: alle verdachte steekproeven worden verzonden naar Microsoft.

|||
|:---|:---|
| **Sleutel** | automaticSampleSubmissionConsent |
| **Gegevenstype** | Tekenreeks |
| **Mogelijke waarden** | geen <br/> veilig (standaard) <br/> alles |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>Automatische beveiligingsinformatie-updates in- of uitschakelen

Hiermee bepaalt u of beveiligingsinformatieupdates automatisch worden geïnstalleerd:

|||
|:---|:---|
| **Sleutel** | automaticDefinitionUpdateEnabled |
| **Gegevenstype** | Booleaanse waarde |
| **Mogelijke waarden** | true (standaard) <br/> onwaar |
|||

## <a name="recommended-configuration-profile"></a>Aanbevolen configuratieprofiel

Om aan de slag te gaan, raden we u aan het volgende configuratieprofiel voor uw bedrijf te gebruiken om te profiteren van alle beveiligingsfuncties die Defender voor Eindpunt biedt.

Het volgende configuratieprofiel is:

- Realtimebeveiliging inschakelen (RTP)
- Geef op hoe de volgende bedreigingstypen worden verwerkt:
  - **Potentieel ongewenste toepassingen (PUA)** worden geblokkeerd
  - **Archiefbommen** (bestand met een hoge compressiesnelheid) worden gecontroleerd op de productlogboeken
- Automatische beveiligingsinformatie-updates inschakelen
- Beveiliging via de cloud inschakelen
- Automatische voorbeeldinzending op niveau `safe` inschakelen

### <a name="sample-profile"></a>Voorbeeldprofiel

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a>Voorbeeld van volledig configuratieprofiel

Het volgende configuratieprofiel bevat vermeldingen voor alle instellingen die in dit document worden beschreven en kunnen worden gebruikt voor meer geavanceerde scenario's waarin u meer controle over het product wilt.

### <a name="full-profile"></a>Volledig profiel

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home"
         },
         {
            "$type":"excludedFileExtension",
            "extension":"pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a>Configuratieprofielvalidatie

Het configuratieprofiel moet een geldig bestand met JSON-indeling zijn. Er zijn een aantal hulpprogramma's die kunnen worden gebruikt om dit te verifiëren. Als u bijvoorbeeld op uw apparaat `python` hebt geïnstalleerd:

```bash
python -m json.tool mdatp_managed.json
```

Als de JSON goed is gevormd, wordt deze met de bovenstaande opdracht terug naar de Terminal uitgevoerd en wordt een exitcode van `0` . Anders wordt een fout weergegeven die het probleem beschrijft en retourneert de opdracht een exitcode van `1` .

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a>Controleren of de mdatp_managed.jsbestand werkt zoals verwacht
Als u wilt controleren of uw /etc/opt/microsoft/mdatp/managed/mdatp_managed.jsop naar behoren werkt, ziet u '[beheerd]' naast deze instellingen:  
- cloud_enabled
- cloud_automatic_sample_submission_consent
- passice_mode_enabled
- real_time_protection_enabled
- automatic_definition_update_enabled

> [!NOTE]
> Als de mdatp_managed.jsin werking treedt, is er geen herstart van de wdavdaemon vereist.

## <a name="configuration-profile-deployment"></a>Implementatie van configuratieprofiel

Nadat u het configuratieprofiel voor uw onderneming hebt gemaakt, kunt u het implementeren via het beheerprogramma dat uw bedrijf gebruikt. Defender voor Eindpunt voor Linux leest de beheerde configuratie uit het *bestand /etc/opt/microsoft/mdatp/managed/mdatp_managed.js.*
