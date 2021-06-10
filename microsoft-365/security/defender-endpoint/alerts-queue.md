---
title: De wachtrij waarschuwingen voor Microsoft Defender voor eindpunten weergeven en ordenen
description: Meer informatie over hoe wachtrijen voor waarschuwingen in Microsoft Defender voor Eindpunt werken en hoe u lijsten met waarschuwingen sorteert en filtert.
keywords: waarschuwingen, wachtrijen, waarschuwingenwachtrij, sorteren, volgorde, filteren, waarschuwingen beheren, nieuw, in uitvoering, opgelost, nieuwste, tijd in wachtrij, ernst, periode, waarschuwingen van microsoft threat experts
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 03/27/2020
ms.technology: mde
ms.openlocfilehash: 48a3ff8dba5bccd62d7d43b295c136a814056a15
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934331"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a>De wachtrij waarschuwingen voor Microsoft Defender voor eindpunten weergeven en ordenen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-alertsq-abovefoldlink) 

In **de wachtrij Waarschuwingen** ziet u een lijst met waarschuwingen die zijn gemarkeerd vanaf apparaten in uw netwerk. Standaard worden in de wachtrij waarschuwingen weergegeven die in de afgelopen 30 dagen in een gegroepeerde weergave zijn weergegeven. De meest recente waarschuwingen worden boven aan de lijst weergegeven, zodat u eerst de meest recente waarschuwingen kunt zien.

> [!NOTE]
> De wachtrij voor waarschuwingen wordt aanzienlijk verminderd met geautomatiseerd onderzoek en herstel, zodat experts voor beveiligingsbewerkingen zich kunnen richten op geavanceerdere bedreigingen en andere hoogwaardige initiatieven. Wanneer een waarschuwing een ondersteunde entiteit bevat voor geautomatiseerd onderzoek (bijvoorbeeld een bestand) in een apparaat met een ondersteund besturingssysteem, kan een geautomatiseerd onderzoek en herstel starten. Zie Overzicht van geautomatiseerde onderzoeken voor meer informatie over [geautomatiseerde onderzoeken.](automated-investigations.md)

Er zijn verschillende opties waar u uit kunt kiezen om de wachtrijweergave voor waarschuwingen aan te passen. 

Op de bovenste navigatie kunt u:

- Gegroepeerde weergave of lijstweergave selecteren
- Kolommen aanpassen om kolommen toe te voegen of te verwijderen 
- De items selecteren die per pagina moeten worden weergegeven
- Navigeren tussen pagina's
- Filters toepassen

![Afbeelding van waarschuwingenwachtrij](images/alerts-queue-list.png)

## <a name="sort-filter-and-group-the-alerts-queue"></a>De waarschuwingenwachtrij sorteren, filteren en groeperen

U kunt de volgende filters toepassen om de lijst met waarschuwingen te beperken en de waarschuwingen beter te bekijken.

### <a name="severity"></a>Ernst

Ernst van waarschuwing | Beschrijving
:---|:---
Hoog </br>(Rood) | Waarschuwingen die vaak worden gezien in verband met geavanceerde permanente bedreigingen (APT). Deze waarschuwingen geven een hoog risico aan vanwege de ernst van de schade die ze kunnen toebrengen aan apparaten. Enkele voorbeelden zijn: activiteiten van referentiediefstalhulpmiddelen, ransomwareactiviteiten die niet aan een groep zijn gekoppeld, geknoei met beveiligingssensoren of schadelijke activiteiten die wijzen op een menselijke tegenstrever.
Gemiddeld </br>(Oranje) | Waarschuwingen van eindpuntdetectie en -respons gedragingen na inbreuk die mogelijk deel uitmaken van een geavanceerde permanente bedreiging (APT). Dit omvat waargenomen gedrag dat typisch is voor aanvalsfasen, afwijkende registerwijziging, uitvoering van verdachte bestanden, enzovoort. Hoewel sommige mogelijk deel uitmaken van interne beveiligingstests, is onderzoek vereist, omdat het mogelijk ook deel uitmaakt van een geavanceerde aanval.
Laag </br>(Geel) | Waarschuwingen over bedreigingen die zijn gekoppeld aan voorkomende malware. Denk bijvoorbeeld aan hackprogramma's, hulpprogramma's voor niet-malware hacken, zoals het uitvoeren van verkenningsopdrachten, het wissen van logboeken, enzovoort, die vaak geen geavanceerde bedreiging aangeven die zich op de organisatie richt. Het kan ook afkomstig zijn van een geïsoleerd beveiligingsprogramma dat is getest door een gebruiker in uw organisatie.
Informatief </br>(Grijs) | Waarschuwingen die mogelijk niet als schadelijk voor het netwerk worden beschouwd, maar die de organisatie meer bewust kunnen maken van mogelijke beveiligingsproblemen.

#### <a name="understanding-alert-severity"></a>Ernst van waarschuwingswaarschuwingen

Microsoft Defender Antivirus (Microsoft Defender AV) en Defender voor eindpuntwaarschuwingen verschillen omdat ze verschillende bereikbereiken vertegenwoordigen.

De ernst van de AV-bedreiging van Microsoft Defender vertegenwoordigt de absolute ernst van de gedetecteerde bedreiging (malware) en wordt toegewezen op basis van het potentiële risico voor het afzonderlijke apparaat, indien geïnfecteerd.

De ernst van de waarschuwing van Defender voor eindpunt geeft de ernst van het gedetecteerde gedrag aan, het werkelijke risico voor het apparaat, maar nog belangrijker het potentiële risico voor de organisatie.

Bijvoorbeeld:

- De ernst van een Waarschuwing van Defender voor Eindpunt over een Microsoft Defender AV-gedetecteerde bedreiging die volledig is voorkomen en het apparaat niet heeft geïnfecteerd, wordt gecategoriseerd als 'Informatief' omdat er geen werkelijke schade was.
- Een waarschuwing over een commerciële malware is gedetecteerd tijdens het uitvoeren, maar geblokkeerd en gesaneerd door Microsoft Defender AV, wordt gecategoriseerd als 'Laag', omdat deze mogelijk enige schade heeft veroorzaakt aan het afzonderlijke apparaat, maar geen bedreiging vormt voor de organisatie.
- Een waarschuwing over malware die tijdens het uitvoeren is gedetecteerd en die niet alleen een bedreiging kan vormen voor het afzonderlijke apparaat, maar ook voor de organisatie, ongeacht of deze uiteindelijk is geblokkeerd, kan worden geclassificeerd als 'Gemiddeld' of 'Hoog'.
- Verdachte waarschuwingen voor gedrag, die niet zijn geblokkeerd of die niet zijn gesaneerd, worden geclassificeerd als 'Laag', 'Gemiddeld' of 'Hoog' volgens dezelfde bedreigingsoverwegingen van de organisatie.

#### <a name="understanding-alert-categories"></a>Waarschuwingscategorieën begrijpen

We hebben de waarschuwingscategorieën opnieuw gedefinieerd om uit te lijnen op de [aanvalstactieken](https://attack.mitre.org/tactics/enterprise/) van de onderneming in de [MITRE ATT-matrix&CK.](https://attack.mitre.org/) Nieuwe categorienamen zijn van toepassing op alle nieuwe waarschuwingen. Bestaande waarschuwingen behouden de vorige categorienamen.

De onderstaande tabel bevat de huidige categorieën en de manier waarop ze over het algemeen worden toe te wijden aan eerdere categorieën. 

| Nieuwe categorie       | NAAM VAN API-categorie   | Gedetecteerde bedreigingsactiviteit of onderdeel                                                                                                 |
|----------------------|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| Verzameling           | Verzameling          | Gegevens voor exfiltratie zoeken en verzamelen                                                                                         |
| Opdracht en besturingselement  | CommandAndControl   | Verbinding maken met netwerkinfrastructuur die door de aanvaller wordt beheerd om gegevens door te geven of opdrachten te ontvangen                                          |
| Toegang tot referenties    | CredentialAccess    | Geldige referenties verkrijgen om de controle over apparaten en andere resources in het netwerk uit te breiden                                       |
| Verdedigingsontwijking      | DefenseEvasion      | Beveiligingsbesturingselementen vermijden door bijvoorbeeld beveiligingsapps uit te schakelen, implantaten te verwijderen en rootkits uit te voeren                        |
| Detectie            | Detectie           | Informatie verzamelen over belangrijke apparaten en resources, zoals beheerderscomputers, domeincontrollers en bestandsservers  |
| Uitvoering            | Uitvoering           | Hulpprogramma's voor aanvallers en schadelijke code starten, waaronder RAT's en backdoors                                                             |
| Exfiltration         | Exfiltration        | Gegevens uit het netwerk extraheren naar een externe, door de aanvaller gecontroleerde locatie                                                         |
| Exploit              | Exploit             | Code en mogelijke benuttingsactiviteit gebruiken                                                                                       |
| Eerste toegang       | InitialAccess       | Eerste toegang krijgen tot het doelnetwerk, meestal met wachtwoord-raden, exploits of phishing-e-mailberichten                      |
| Zijbeweging     | LateralMovement     | Verplaatsen tussen apparaten in het doelnetwerk om kritieke bronnen te bereiken of netwerk persistentie te krijgen                                |
| Malware              | Malware             | Backdoors, trojaanse paarden en andere typen schadelijke code                                                                                 |
| Persistentie          | Persistentie         | Extensibility points (ASEP's) voor automatisch starten maken om actief te blijven en systeemstarten te overleven                                        |
| Escalatie van bevoegdheden | PrivilegeEscalation | Hogere machtigingsniveaus voor code verkrijgen door deze uit te voeren in de context van een bevoorrecht proces of account                         |
| Ransomware           | Ransomware          | Malware die bestanden versleutelt en betaling afperst om de toegang te herstellen                                                                     |
| Verdachte activiteit  | SuspiciousActivity  | Atypische activiteit die malwareactiviteit of een deel van een aanval kan zijn                                                                 |
| Ongewenste software    | Ongewenste software    | Apps en apps met een lage reputatie die van invloed zijn op de productiviteit en de gebruikerservaring; gedetecteerd als potentieel ongewenste toepassingen (PUA's) |

### <a name="status"></a>Status

U kunt ervoor kiezen om de lijst met waarschuwingen te beperken op basis van hun status.

### <a name="investigation-state"></a>Onderzoekstoestand

Komt overeen met de geautomatiseerde onderzoekstoestand.

### <a name="category"></a>Categorie

U kunt ervoor kiezen om de wachtrij te filteren om specifieke typen schadelijke activiteiten weer te geven.

### <a name="assigned-to"></a>Toegewezen aan

U kunt kiezen tussen het weergeven van waarschuwingen die aan u zijn toegewezen of automatisering.

### <a name="detection-source"></a>Detectiebron

Selecteer de bron die de waarschuwingsdetectie heeft geactiveerd. Microsoft Threat Experts voorbeeld van deelnemers kunnen nu detecties filteren en zien van de nieuwe door bedreigingsdeskundigen beheerde huntingservice.

>[!NOTE]
>Het antivirusfilter wordt alleen weergegeven als apparaten Microsoft Defender Antivirus als het standaard antimalware-product voor realtimebeveiliging.

| Detectiebron                  | API-waarde                  |
|-----------------------------------|----------------------------|
| Sensoren van derden                 | ThirdPartySensors          |
| Antivirus                         | WindowsDefenderAv          |
| Geautomatiseerd onderzoek           | AutomatedInvestigation     |
| Aangepaste detectie                  | CustomDetection            |
| Aangepaste TI                         | CustomerTI                 |
| EDR                               | WindowsDefenderAtp         |
| Microsoft 365 Defender            | MTP                        |
| Microsoft Defender voor Office 365 | OfficeATP                  |
| Microsoft Threat Experts          | ThreatExperts              |
| SmartScreen                       | WindowsDefenderSmartScreen |

### <a name="os-platform"></a>BESTURINGSSYSTEEM-platform

Beperk de wachtrijweergave voor waarschuwingen door het besturingssysteemplatform te selecteren dat u wilt onderzoeken.

### <a name="device-group"></a>Apparaatgroep

Als u specifieke apparaatgroepen hebt die u wilt controleren, kunt u de groepen selecteren om de wachtrijweergave voor waarschuwingen te beperken. 

### <a name="associated-threat"></a>Gekoppelde bedreiging

Gebruik dit filter om u te richten op waarschuwingen die betrekking hebben op bedreigingen met een hoog profiel. U ziet de volledige lijst met high-profile bedreigingen in [Threat Analytics.](threat-analytics.md)

## <a name="related-topics"></a>Verwante onderwerpen

- [Waarschuwingen voor Microsoft Defender voor eindpunten beheren](manage-alerts.md)
- [Microsoft Defender onderzoeken voor eindpuntwaarschuwingen](investigate-alerts.md)
- [Een bestand onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt](investigate-files.md)
- [Apparaten onderzoeken in de lijst Microsoft Defender voor eindpuntapparaten](investigate-machines.md)
- [Een IP-adres onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt](investigate-ip.md)
- [Een domein onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt](investigate-domain.md)
- [Een gebruikersaccount onderzoeken in Microsoft Defender voor Eindpunt](investigate-user.md)
