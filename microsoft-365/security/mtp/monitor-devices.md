---
title: Device monitoring & Reporting-Beveiligingscentrum
description: Hier wordt beschreven hoe u uw apparaten veilig, up-to-date en mogelijke bedreigingen in uw organisatie kunt beschermen
keywords: beveiliging, malware, Microsoft 365, M365, beveiliging centrum, monitor, rapport, apparatuur
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0854953ccd910c5eafd4c643b95f255450fd1601
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413744"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Apparaten volgen en rapporteren in het Microsoft 365-Beveiligingscentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Zorg dat uw apparaten veilig, up-to-date en potentiële bedreigingen in het Microsoft 365-Beveiligingscentrum.

## <a name="view-device-alerts"></a>Waarschuwingen voor apparaten weergeven

U ontvangt actuele meldingen over de overtredings activiteit en andere bedreigingen op uw apparaten in Microsoft Defender ATP (beschikbaar met een E5-licentie). Microsoft 365-Beveiligingscentrum controleert deze meldingen op een hoog niveau met behulp van de door u gewenste werkstroom.

### <a name="monitor-high-impact-alerts"></a>Waarschuwingen voor hoge impact volgen

Elke Microsoft Defender ATP-waarschuwing heeft een corresponderende Ernst (hoog, normaal, laag of informatie). Dit geeft de potentiële impact op uw netwerk aan als ze niet aanwezig zijn.  

U kunt de kaart voor de **geluidssignaal** van uw apparaat gebruiken om specifiekere meldingen te benadrukken en mogelijk direct antwoord te vragen. Op deze kaart kunt u meer informatie weergeven op de portal Microsoft Defender-Beveiligingscentrum.

![Kaart met ernst van apparaat-waarschuwingen](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>Meer informatie over de bronnen van waarschuwingen

Microsoft Defender ATP maakt gebruik van gegevens uit tal van beveiligings sensies en intelligence-bronnen voor het genereren van waarschuwingen. Dit kan bijvoorbeeld de detectie informatie van Microsoft Defender antivirus en van malware van derden gebruiken. U kunt ook uw eigen aangepaste bedreigings informatie gebruiken die beschikbaar is via de API van de webservice.

Op de kaart met de detectie bronnen voor **device-meldingen** ziet u de distributie van waarschuwingen per bron. Activiteiten bijhouden met betrekking tot bepaalde bronnen, met name de aangepaste bronnen. U kunt ook de kaart gebruiken om te focussen op meldingen die afkomstig zijn van sensoren die niet zijn geconfigureerd om schadelijke activiteiten of onderdelen automatisch te blokkeren.

![Kaart voor detectie bronnen voor apparaat voor meldingen](../../media/device-alert-detection-sources.png)

Op deze kaart kunt u meer informatie weergeven op de portal Microsoft Defender-Beveiligingscentrum.

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>Meer informatie over de typen bedreigingen die waarschuwingen activeren

In Microsoft Defender ATP wordt elke waarschuwing in een categorie gesorteerd in een categorie voor een bepaalde fase in de hack-ketting of het type risico onderdeel. Een gedetecteerde bedreiging is bijvoorbeeld mogelijk gecategoriseerd als ' zijdelings verplaatsings actie ' om aan te geven dat er andere apparaten in het netwerk konden worden bereikt. De activiteit is waarschijnlijk opgetreden nadat een hacker een initiële foothold heeft verkregen. Wanneer deze worden gedetecteerd, kan een onderdeel van de bedreiging algemeen als malware of specifiek risico type worden geclassificeerd. Specifieke voorbeelden van Ransomware, referentie diefstal of andere typen kwaadaardige en ongewenste software.

De kaart **bedreigings categorieën voor apparaten** toont de distributie van waarschuwingen in deze categorieën. Met deze informatie kunt u bedreigings activiteiten identificeren, zoals diefstal van referenties, die meestal hoger zijn dan de pogingen van sociale engineering. U kunt ook controleren op mogelijk destructieve bedreigingen, zoals Ransomware.

![Kaart bedreiging categorieën voor apparatuur](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>Actieve waarschuwingen controleren

De **melding status** kaart van het apparaat geeft het aantal waarschuwingen aan dat nog niet is opgelost en waarvan de aandacht moet worden besteed. Op deze kaart kunt u meer informatie weergeven op de portal Microsoft Defender-Beveiligingscentrum.

![Meldings status kaart van apparaat](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>De classificatie van opgeloste waarschuwingen controleren

Wanneer u een Microsoft Defender ATP-waarschuwing verhelpt, kunnen uw beveiligingspersoneel opgeven of een waarschuwing is geverifieerd als:

* Een echte waarschuwing waarin de feitelijke activiteiten van de overtreding of de bedreigings onderdelen worden aangegeven
* Een onjuiste waarschuwing met een onjuiste detectie van normaal activiteiten

De **classificatie** kaart voor melding van apparaat geeft aan of de opgeloste waarschuwingen zijn geclassificeerd als waar of onwaar. Op deze kaart kunt u meer informatie weergeven op de portal Microsoft Defender-Beveiligingscentrum.

Opmerking: in sommige gevallen is classificatie informatie niet beschikbaar voor bepaalde meldingen.

![Classificatie kaart voor het ontvangen van hardware](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>Controle bepaling van opgeloste waarschuwingen

Als u een melding wilt ontvangen, ongeacht of een waarschuwing waar of onwaar is tijdens de oplossing, kunnen uw beveiligingspersoneel een bepaling leveren. Een bepaling geeft het type normale of schadelijke activiteit aan dat is gevonden bij het valideren van de waarschuwing.

De kaart voor de **waarschuwings analyse** van uw apparaat toont de bepaling die voor elke melding wordt weergegeven.

* **Apt**: geavanceerde permanente bedreiging, waarmee wordt aangegeven dat de gedetecteerde activiteit of de bedreiging onderdeel is onderdeel van een verfijnde geschaade schending, ontwikkeld voor het verkrijgen van een foothold in de betreffende netwerk  
* **Malware**: schadelijk bestand of programmacode
* **Beveiligingspersoneel**: normale activiteit uitgevoerd door beveiligingspersoneel
* **Beveiliging testen**: activiteit of onderdelen die zijn ontworpen om feitelijke bedreigingen te simuleren en om meldingen te activeren en waarschuwingen te genereren
* **Ongewenste software**: apps en andere software die niet als schadelijk worden beschouwd, maar op een andere wijze beleidsregels of acceptabele gebruiks normen schenden
* **Andere**bepalingen die niet onder de geleverde soorten vallen.

Vanaf dit kaartje kunt u meer informatie weergeven in Microsoft Defender-Beveiligingscentrum.

![Waarschuwings kaart voor apparaat](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>Begrijpen welke apparaten risico lopen

**Apparaat-bescherming** toont het risiconiveau voor apparaten. Het risiconiveau is gebaseerd op factoren zoals het type en de ernst van waarschuwingen op het apparaat.

![Hardware-beschermings kaart](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>De status van intune-beheerde apparaten controleren en rapporteren

De volgende rapporten bevatten gegevens van apparaten die zijn geregistreerd voor intune. Gegevens van niet-geregistreerde apparaten zijn niet inbegrepen. Alleen globale beheerders kunnen deze kaarten weergeven.

InTune geregistreerde apparaatgegevens zijn onder meer:

* Apparaatcompatibiliteit
* Apparaten met actieve malware
* Typen malware op apparaten
* Malware op apparaten
* Apparaten met detectie van malware
* Gebruikers met detectie van malware

### <a name="monitor-device-compliance"></a>Naleving van apparaat controleren

**Naleving van apparaat** laat zien hoeveel apparaten zijn geregistreerd voor intune-afnaleving met het configuratiebeleid.

![Hardware compliantie kaart](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>Apparaten detecteren met detectie van malware

**Detectie van detectie van apparaat** geeft het aantal niet-geregistreerde apparaten met malware aan dat niet volledig is opgelost. Het gebrek aan de oplossing kan zijn vanwege acties die in behandeling zijn, een herstart, een volledige scan, handmatige actie van gebruikers of als de herstelbewerking is voltooid.

![Kaart detectie van apparaat voor malware](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>Meer informatie over de verschillende typen malware

Met de **typen malware op apparaten** worden verschillende soorten malware weergegeven die zijn gedetecteerd op apparaten die zijn ingeschreven in intune. U kunt elk type onderzoeken in het Microsoft 365-Beveiligingscentrum.

![Type malware op de kaart apparaten](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>Meer informatie over de specifieke malware die op uw apparaten is gedetecteerd

**Malware op apparaten** biedt een lijst met de specifieke malware die op uw apparaten is gedetecteerd.

![Malware op apparaten kaart](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>Begrijpen welke apparaten de beste malware hebben

**Apparaten met detectie van malware** tonen welke apparaten de meeste detectie van malware hebben. in het Microsoft 365-Beveiligingscentrum kunt u nagaan of er malware actief is die het apparaat gebruikt en de Beheerstatus in intune.

![Apparaten met detectie van detectie van malware](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>Begrijpen welke gebruikers apparaten met de meeste malware hebben

**Gebruikers met malware-detectie** geven gebruikers weer met apparaten die de meeste detectie van malware hebben. In het Microsoft 365-Beveiligingscentrum kunt u zien hoeveel apparaten aan elke gebruiker zijn toegewezen en meer informatie over elk apparaat en het type malware.

![Gebruikers met detectie Card voor malware](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a>Implementatie en detectie van aanvals regels controleren en beheren

Regels voor het beperken van een [aanval (ASR)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) helpen voorkomen dat acties en apps die meestal door misbruik worden gebruikt, malware willen infecteren. Met deze regels wordt bepaald wanneer en hoe de uitvoerbare bestanden kunnen worden uitgevoerd. U kunt voorkomen dat u een gedownload uitvoerbare uitvoerbare uitvoerbare uitvoerbare uitvoerbare uitvoerbare bestanden uitvoert, Win32 API-oproepen van Office-macro's blokkeert of processen die worden uitgevoerd vanaf USB-stations blokkeren.

![Beperking voor oppervlakte van aanval](../../media/attack-surface-reduction-rules.png)

De kaart **reductie regels** van een aanval biedt een overzicht van de implementatie van regels op uw apparaten.

De bovenste balk van de kaart toont het totale aantal apparaten dat zich in de volgende implementatie modi bevindt:

* **Blokmodus**: apparaten met minimaal één regel geconfigureerd om gedetecteerde activiteiten blokkeren
* **Controlemodus**: apparaten zonder regels die zijn ingesteld voor het blokkeren van gedetecteerde activiteiten, maar er is minimaal één regel ingesteld om controle gedetecteerde activiteiten te controleren  
* **Uitgeschakeld**: apparaten met alle ASR-regels uitgeschakeld

In het onderste gedeelte van dit kaartje worden instellingen weergegeven op regel op uw apparaten. Met elke balk wordt het aantal apparaten aangegeven dat is ingesteld op blokkeren, controleren en controleren of de regel volledig is uitgeschakeld.

### <a name="view-asr-detections"></a>Detectie van ASR weergeven

Als u gedetailleerde informatie over de detectie van de ASR-regel wilt weergeven in uw netwerk, selecteert u **detectie van detectie weergeven** op de kaart voor het risico voor **oppervlakte-aanval** . Het tabblad **detectie** op de pagina gedetailleerd rapport wordt geopend.

![Tabblad detectie](../../media/detections-tab.png)

De grafiek boven aan de pagina toont detecties van detectie van tijds stapels die zijn geblokkeerd of gecontroleerd. De tabel onderaan bevat de meest recente detecties. Gebruik de volgende informatie op de tabel om inzicht te krijgen in de aard van de detecties:

* **Vastgesteld bestand**: het bestand, meestal een script of een document, waarvan de inhoud de inhoud van de verdachte aanval heeft geactiveerd.
* **Regel**: naam waarmee de aanvals activiteiten worden beschreven die de regel is bedoeld om te worden onderschept. Meer informatie over bestaande ASR-regels
* **Bron-app**: de toepassing die inhoud heeft geladen of uitgevoerd met de activering van de verdachte aanvals activiteit. Het kan een legitieme toepassing zijn, zoals een webbrowser, een Office-toepassing of een systeem hulpmiddel zoals PowerShell
* **Uitgever**: de leverancier die de bron-app heeft vrijgegeven

### <a name="review-device-asr-rule-settings"></a>Instellingen voor ASR-regel voor apparaat controleren

Ga op de pagina het rapport **regels voor risicobeperking** voor een aanval naar het tabblad **configuratie** om regelinstellingen voor afzonderlijke apparaten te bekijken. Selecteer een apparaat voor gedetailleerde informatie over het feit of elke regel in de blokmodus, de controlemodus of helemaal is uitgeschakeld.

![Het tabblad Configuratie](../../media/configuration-tab.png)

Microsoft intune biedt beheerfuncties voor de ASR-regels. Als u uw instellingen wilt bijwerken, selecteert u **aan de slag** onder **apparaten configureren** op het tabblad om Apparaatbeheer te openen op intune.

### <a name="exclude-files-from-asr-rules"></a>Bestanden uitsluiten van ASR-regels

Microsoft 365-Beveiligingscentrum verzamelt de namen van de [bestanden die u mogelijk niet wilt uitsluiten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) van detecties voor de risico regels. Door bestanden uit te sluiten, kunt u ongunstige detecties beperken en de beperking voor risico oppervlakte beperking in de blokmodus vertrouwen.

De uitsluitingen worden beheerd op Microsoft intune, maar Microsoft 365 Beveiligingscentrum biedt een hulpmiddel waarmee u de bestanden kunt begrijpen. Als u wilt beginnen met het verzamelen van bestanden voor uitsluiting, gaat u naar het tabblad **Uitsluitingen toevoegen** op de rapportpagina regels voor risicobeperking van de **aanval** .

>[!NOTE]  
>Met het hulpprogramma worden detecties van alle aanvals regels geanalyseerd, maar [slechts enkele regels ondersteunen uitgesloten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)verbindingen.

![Tabblad uitzonderingen toevoegen](../../media/add-exclusions-tab.png)

De tabel bevat een overzicht van alle bestandsnamen die door uw aanvals regels voor oppervlakte worden gedetecteerd. U kunt bestanden selecteren om de gevolgen van de uitsluiting ervan te controleren:

* Hoeveel minder detecteren
* Hoeveel minder apparaten de detecties rapporteren

Als u een lijst met de geselecteerde bestanden met hun volledige paden voor uitsluiting wilt weergeven, selecteert u **uitsluitings paden aanvragen**.

Logboeken voor de inlog regels voor ASR-regels die **van het Windows Local Security Authority Subsystem (lsass.exe) worden gestolen** de bron-app **lsass.exe**vastleggen. Het is een normaal systeembestand, maar vastgelegd als het gevonden bestand. De gegenereerde lijst met uitgesloten paden bevat daarom het bestand. Als u het bestand wilt uitsluiten dat deze regel heeft geactiveerd in plaats van **lsass.exe**, gebruikt u het pad naar de bron-app in plaats van het gevonden bestand.

U kunt de bron-app vinden door de volgende [geavanceerde zoekopdracht](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) uit te voeren voor deze specifieke regel (aangeduid met regel-id 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a>Bestanden controleren op uitsluiting

Voordat u een bestand uit ASR uitsluit, is het raadzaam om het bestand te controleren om te bepalen of het bestand daadwerkelijk niet schadelijk is.

Als u een bestand wilt controleren, gebruikt u de [pagina met bestandsinformatie](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) in Microsoft Defender-Beveiligingscentrum. Op de pagina vindt u informatie over de prevalentie en de bezorgings verhouding VirusTotal antivirus. U kunt de pagina ook gebruiken om het bestand in te dienen voor uitgebreide analyse.

Als u een gevonden bestand wilt zoeken in Microsoft Defender-Beveiligingscentrum, zoekt u alle ASR-detecties met behulp van de volgende geavanceerde zoekopdracht:

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

Gebruik de **UDDI-of de** **InitiatingProcessSHA1** in de zoekresultaten om het bestand te zoeken met behulp van de universele zoekbalk in Microsoft Defender-Beveiligingscentrum.
