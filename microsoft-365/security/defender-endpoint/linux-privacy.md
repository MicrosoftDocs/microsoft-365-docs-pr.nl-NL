---
title: Privacy voor Microsoft Defender ATP voor Linux
description: Privacybesturingselementen, het configureren van beleidsinstellingen die van invloed zijn op de privacy en informatie over de diagnostische gegevens die worden verzameld in Microsoft Defender ATP voor Linux.
keywords: microsoft, defender, atp, linux, privacy, diagnostische
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b56e8a74875b3377b6f3228bbefb339680dbc6e1
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187779"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-for-linux"></a>Privacy voor Microsoft Defender voor Eindpunt voor Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft doet er alles aan om u de informatie en besturingselementen te bieden die u nodig hebt om keuzes te maken over hoe uw gegevens worden verzameld en gebruikt wanneer u Defender voor Eindpunt voor Linux gebruikt.

In dit onderwerp worden de privacybesturingselementen beschreven die beschikbaar zijn in het product, hoe u deze besturingselementen beheert met beleidsinstellingen en meer informatie over de gegevensgebeurtenissen die worden verzameld.

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-for-linux"></a>Overzicht van privacybesturingselementen in Microsoft Defender voor Eindpunt voor Linux

In deze sectie worden de privacybesturingselementen beschreven voor de verschillende typen gegevens die door Defender voor Eindpunt voor Linux worden verzameld.

### <a name="diagnostic-data"></a>Diagnostische gegevens

Diagnostische gegevens worden gebruikt om Defender voor Eindpunt veilig en up-to-date te houden, problemen op te sporen, te diagnosticeren en op te lossen, en om productverbeteringen aan te brengen.

Sommige diagnostische gegevens zijn vereist, terwijl andere diagnostische gegevens optioneel zijn. We geven u de mogelijkheid om te kiezen of u ons vereiste of optionele diagnostische gegevens wilt sturen via het gebruik van privacy-instellingen, zoals beleidsinstellingen voor organisaties.

Er zijn twee niveaus met diagnostische gegevens voor Defender voor Endpoint-clientsoftware waar u uit kunt kiezen:

* **Vereist:** De minimale gegevens die nodig zijn om Defender voor Eindpunt veilig, up-to-date te houden en te presteren zoals verwacht op het apparaat waarop het is geïnstalleerd.

* **Optioneel:** Aanvullende gegevens waarmee Microsoft productverbeteringen kan aanbrengen en uitgebreide informatie biedt om problemen op te sporen, te diagnosticeren en te verhelpen.

Standaard worden alleen vereiste diagnostische gegevens naar Microsoft verzonden.

### <a name="cloud-delivered-protection-data"></a>Cloud geleverde beveiligingsgegevens

Cloudbezorgde beveiliging wordt gebruikt om meer en snellere beveiliging te bieden met toegang tot de meest recente beveiligingsgegevens in de cloud.

Het inschakelen van de door de cloud geleverde beveiligingsservice is optioneel, maar het wordt ten zeerste aanbevolen omdat deze belangrijke bescherming biedt tegen malware op uw eindpunten en in uw netwerk.

### <a name="sample-data"></a>Voorbeeldgegevens

Voorbeeldgegevens worden gebruikt om de beveiligingsmogelijkheden van het product te verbeteren door verdachte steekproeven van Microsoft te verzenden, zodat ze kunnen worden geanalyseerd. Automatische voorbeeldinzending inschakelen is optioneel.

Er zijn drie niveaus voor het beheren van voorbeeldinzending:

- **Geen:** er worden geen verdachte steekproeven ingediend bij Microsoft.
- **Veilig:** alleen verdachte steekproeven die geen persoonlijk identificeerbare gegevens (PII) bevatten, worden automatisch verzonden. Dit is de standaardwaarde voor deze instelling.
- **Alle**: alle verdachte steekproeven worden verzonden naar Microsoft.

## <a name="manage-privacy-controls-with-policy-settings"></a>Privacybesturingselementen met beleidsinstellingen beheren

Als u een IT-beheerder bent, kunt u deze besturingselementen configureren op ondernemingsniveau. 

De privacybesturingselementen voor de verschillende typen gegevens die in de vorige sectie worden beschreven, worden gedetailleerd beschreven in [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).

Net als bij nieuwe beleidsinstellingen moet u deze zorgvuldig testen in een beperkte, gecontroleerde omgeving om ervoor te zorgen dat de instellingen die u configureert het gewenste effect hebben voordat u de beleidsinstellingen breder implementeert in uw organisatie.

## <a name="diagnostic-data-events"></a>Diagnostische gegevensgebeurtenissen

In deze sectie wordt beschreven wat wordt beschouwd als vereiste diagnostische gegevens en wat wordt beschouwd als optionele diagnostische gegevens, samen met een beschrijving van de gebeurtenissen en velden die worden verzameld.

### <a name="data-fields-that-are-common-for-all-events"></a>Gegevensvelden die gebruikelijk zijn voor alle gebeurtenissen
Er zijn gegevens over gebeurtenissen die voor alle gebeurtenissen geldt, ongeacht het subtype van de categorie of gegevens. 

De volgende velden worden algemeen beschouwd voor alle gebeurtenissen:

| Veld                   | Beschrijving |
| ----------------------- | ----------- |
| platform                | De algemene classificatie van het platform waarop de app wordt uitgevoerd. Hiermee kan Microsoft bepalen op welke platforms een probleem kan optreden, zodat het correct kan worden geprioriteerd. |
| machine_guid            | Unieke id die is gekoppeld aan het apparaat. Hiermee kan Microsoft bepalen of problemen van invloed zijn op een selecte set installaties en hoeveel gebruikers van invloed zijn. |
| sense_guid              | Unieke id die is gekoppeld aan het apparaat. Hiermee kan Microsoft bepalen of problemen van invloed zijn op een selecte set installaties en hoeveel gebruikers van invloed zijn. |
| org_id                  | Unieke id die is gekoppeld aan de onderneming waar het apparaat deel van uitmaken. Hiermee kan Microsoft bepalen of problemen van invloed zijn op een selecte set ondernemingen en hoeveel ondernemingen van invloed zijn. |
| hostnaam                | Naam van lokaal apparaat (zonder DNS-achtervoegsel). Hiermee kan Microsoft bepalen of problemen van invloed zijn op een selecte set installaties en hoeveel gebruikers van invloed zijn. |
| product_guid            | Unieke id van het product. Hiermee kan Microsoft onderscheid maken tussen problemen die van invloed zijn op verschillende smaken van het product. |
| app_version             | Versie van de Defender voor Endpoint voor Linux-toepassing. Hiermee kan Microsoft bepalen welke versies van het product een probleem laten zien, zodat het correct kan worden geprioriteerd.|
| sig_version             | Versie van beveiligingsinformatiedatabase. Hiermee kan Microsoft bepalen welke versies van de beveiligingsintelligentie een probleem laten zien, zodat deze correct kan worden geprioriteerd. |
| supported_compressions  | Lijst met compressiealgoritmen die door de toepassing worden ondersteund, `['gzip']` bijvoorbeeld. Hiermee kan Microsoft begrijpen welke typen compressies kunnen worden gebruikt wanneer het communiceert met de toepassing. |
| release_ring            | Bel waar het apparaat aan is gekoppeld (bijvoorbeeld Insider Fast, Insider Slow, Productie). Hiermee kan Microsoft bepalen op welke releasering een probleem kan optreden, zodat deze correct kan worden geprioriteerd. |

### <a name="required-diagnostic-data"></a>Verplichte diagnostische gegevens

**Vereiste diagnostische gegevens** zijn de minimale gegevens die nodig zijn om Defender voor Eindpunt veilig, up-to-date te houden en te presteren zoals verwacht op het apparaat waarop het is geïnstalleerd.

Vereiste diagnostische gegevens helpen bij het identificeren van problemen met Microsoft Defender voor eindpunten die mogelijk betrekking hebben op een apparaat- of softwareconfiguratie. Het kan bijvoorbeeld helpen bepalen of een Defender voor Eindpunt-functie vaker vast loopt op een bepaalde versie van het besturingssysteem, met nieuw geïntroduceerde functies of wanneer bepaalde Functies van Defender voor Eindpunt zijn uitgeschakeld. Vereiste diagnostische gegevens helpen Microsoft deze problemen sneller te detecteren, te diagnosticeren en op te lossen, zodat de gevolgen voor gebruikers of organisaties afnemen.

#### <a name="software-setup-and-inventory-data-events"></a>Software-instellingen en inventarisatiegegevensgebeurtenissen

**Microsoft Defender voor endpoint-installatie /de installatie verwijderen**

De volgende velden worden verzameld:

| Veld            | Beschrijving |
| ---------------- | ----------- |
| correlation_id   | Unieke id die is gekoppeld aan de installatie. |
| Versie          | Versie van het pakket. |
| ernst         | Ernst van het bericht (bijvoorbeeld Informatief). |
| code             | Code die de bewerking beschrijft. |
| tekst             | Aanvullende informatie die is gekoppeld aan de productinstallatie. |

**Configuratie van Microsoft Defender voor eindpunt**

De volgende velden worden verzameld:

| Veld                                               | Beschrijving |
| --------------------------------------------------- | ----------- |
| antivirus_engine.enable_real_time_protection        | Of real-time beveiliging is ingeschakeld op het apparaat of niet. |
| antivirus_engine.passive_mode                       | Of passieve modus is ingeschakeld op het apparaat of niet. |
| cloud_service.enabled                               | Of beveiliging in de cloud is ingeschakeld op het apparaat of niet. |
| cloud_service.time-out                               | Time-out wanneer de toepassing communiceert met de Defender for Endpoint-cloud. |
| cloud_service.heartbeat_interval                    | Interval tussen opeenvolgende hartslagen die door het product naar de cloud zijn verzonden. |
| cloud_service.service_uri                           | URI gebruikt om te communiceren met de cloud. |
| cloud_service.diagnostic_level                      | Diagnostisch niveau van het apparaat (vereist, optioneel). |
| cloud_service.automatic_sample_submission           | Automatische voorbeeldinzending van het apparaat (geen, veilig, alles). |
| edr.early_preview                                   | Of het apparaat EDR early preview-functies moet uitvoeren. |
| edr.group_id                                        | Groepsaanduiding die wordt gebruikt door het detectie- en antwoordonderdeel. |
| edr.tags                                            | Door de gebruiker gedefinieerde tags. |
| functies. \[ optionele functienaam\]                  | Lijst met voorbeeldfuncties, samen met of deze zijn ingeschakeld of niet. |

#### <a name="product-and-service-usage-data-events"></a>Gebruiksgebeurtenissen van producten en services

**Beveiligingsinformatieupdaterapport**

De volgende velden worden verzameld:

| Veld            | Beschrijving |
| ---------------- | ----------- |
| from_version     | Oorspronkelijke versie van beveiligingsinformatie. |
| to_version       | Nieuwe versie van beveiligingsinformatie. |
| status           | Status van de update die het succes of de fout aangeeft. |
| using_proxy      | Of de update is uitgevoerd via een proxy. |
| fout            | Foutcode als de update is mislukt. |
| reason           | Foutbericht als de update is mislukt. |

#### <a name="product-and-service-performance-data-events"></a>Prestatiegebeurtenissen van producten en services

**Statistieken over kernelextensie**

De volgende velden worden verzameld:

| Veld            | Beschrijving |
| ---------------- | ----------- |
| Versie          | Versie van Defender voor Eindpunt voor Linux. |
| instance_id      | Unieke id gegenereerd bij opstarten van kernelextensie. |
| trace_level      | Het niveau van de kernelextensie traceren. |
| subsysteem        | Het onderliggende subsysteem dat wordt gebruikt voor realtime beveiliging. |
| ipc.connect     | Het aantal verbindingsaanvragen dat door de kernelextensie is ontvangen. |
| ipc.rejects      | Het aantal verbindingsaanvragen dat is geweigerd door de kernelextensie. |
| ipc.connected    | Of er een actieve verbinding is met de kernelextensie. |

#### <a name="support-data"></a>Ondersteuningsgegevens

**Diagnostische logboeken**

Diagnostische logboeken worden alleen verzameld met toestemming van de gebruiker als onderdeel van de functie voor het indienen van feedback. De volgende bestanden worden verzameld als onderdeel van de ondersteuningslogboeken:

- Alle bestanden onder */var/log/microsoft/mdatp*
- Subset van bestanden onder */etc/opt/microsoft/mdatp* die worden gemaakt en gebruikt door Defender voor Eindpunt voor Linux
- Productinstallatie- en verwijderingslogboeken onder */var/log/microsoft_mdatp_ \* .log*

### <a name="optional-diagnostic-data"></a>Optionele diagnostische gegevens

**Optionele diagnostische gegevens** zijn aanvullende gegevens waarmee Microsoft productverbeteringen kan aanbrengen en uitgebreide informatie biedt om problemen op te sporen, te diagnosticeren en op te lossen.

Als u ervoor kiest ons optionele diagnostische gegevens te sturen, worden hierbij ook vereiste diagnostische gegevens opgenomen.

Voorbeelden van optionele diagnostische gegevens zijn gegevens die Microsoft verzamelt over productconfiguratie (bijvoorbeeld het aantal uitsluitingen dat is ingesteld op het apparaat) en productprestaties (statistische metingen over de prestaties van onderdelen van het product).

#### <a name="software-setup-and-inventory-data-events"></a>Software-instellingen en inventarisatiegegevensgebeurtenissen

**Configuratie van Microsoft Defender voor eindpunt**

De volgende velden worden verzameld:

| Veld                                              | Beschrijving |
| -------------------------------------------------- | ----------- |
| connection_retry_timeout                           | Time-out van verbinding opnieuw proberen bij communicatie met de cloud. |
| file_hash_cache_maximum                            | Grootte van de productcache. |
| crash_upload_daily_limit                           | Limiet van crashlogboeken die dagelijks worden geüpload. |
| antivirus_engine.exclusions[].is_directory         | Of de uitsluiting van scannen een adreslijst is of niet. |
| antivirus_engine.exclusions[].path                 | Pad dat niet is gescand. |
| antivirus_engine.exclusions[].extension            | Extensie uitgesloten van scannen. |
| antivirus_engine.exclusions[].naam                 | Naam van het bestand dat niet kan worden gescand. |
| antivirus_engine.scan_cache_maximum                | Grootte van de productcache. |
| antivirus_engine.maximum_scan_threads              | Maximum aantal threads dat wordt gebruikt voor scannen. |
| antivirus_engine.threat_restoration_exclusion_time | Time-out voordat een bestand dat uit de quarantaine is hersteld, opnieuw kan worden gedetecteerd. |
| filesystem_scanner.full_scan_directory             | Volledige scanmap. |
| filesystem_scanner.quick_scan_directories          | Lijst met directories die in quick scan worden gebruikt. |
| edr.latency_mode                                   | De latentiemodus die wordt gebruikt door het detectie- en antwoordonderdeel. |
| edr.proxy_address                                  | Proxyadres dat wordt gebruikt door het detectie- en antwoordonderdeel. |

**Configuratie van Microsoft Auto-Update**

De volgende velden worden verzameld:

| Veld                       | Beschrijving |
| --------------------------- | ----------- |
| how_to_check                | Hiermee bepaalt u hoe productupdates worden gecontroleerd (bijvoorbeeld automatisch of handmatig). |
| channel_name                | Kanaal bijwerken dat is gekoppeld aan het apparaat. |
| manifest_server             | Server die wordt gebruikt voor het downloaden van updates. |
| update_cache                | Locatie van de cache die wordt gebruikt voor het opslaan van updates. |

### <a name="product-and-service-usage"></a>Gebruik van producten en services

#### <a name="diagnostic-log-upload-started-report"></a>Rapport voor het uploaden van diagnostisch logboek gestart

De volgende velden worden verzameld:

| Veld            | Beschrijving |
| ---------------- | ----------- |
| sha256           | SHA256-id van het ondersteuningslogboek. |
| grootte             | Grootte van het ondersteuningslogboek. |
| original_path    | Pad naar het ondersteuningslogboek (altijd onder */var/opt/microsoft/mdatp/wdavdiag/*). |
| opmaak           | Opmaak van het ondersteuningslogboek. |

#### <a name="diagnostic-log-upload-completed-report"></a>Rapport voor het uploaden van diagnostisch logboek voltooid

De volgende velden worden verzameld:

| Veld            | Beschrijving |
| ---------------- | ----------- |
| request_id       | Correlatie-id voor de aanvraag voor het uploaden van het ondersteuningslogboek. |
| sha256           | SHA256-id van het ondersteuningslogboek. |
| blob_sas_uri     | URI die door de toepassing wordt gebruikt om het ondersteuningslogboek te uploaden. |

#### <a name="product-and-service-performance-data-events"></a>Prestatiegebeurtenissen van producten en services

**Onverwacht afsluiten toepassing (crash)**

Onverwacht afsluiten van toepassing (crash) en de status van de toepassing wanneer dit gebeurt.

**Statistieken over kernelextensie**

De volgende velden worden verzameld:

| Veld                          | Beschrijving |
| ------------------------------ | ----------- |
| pkt_ack_timeout                | De volgende eigenschappen zijn statistische numerieke waarden, die het aantal gebeurtenissen vertegenwoordigen dat is gebeurd sinds het opstarten van de kernelextensie. |
| pkt_ack_conn_timeout             | |
| ipc.ack_pkts                     | |
| ipc.nack_pkts                    | |
| ipc.send.ack_no_conn             | |
| ipc.send.nack_no_conn            | |
| ipc.send.ack_no_qsq              | |
| ipc.send.nack_no_qsq             | |
| ipc.ack.no_space                 | |
| ipc.ack.time-out                  | |
| ipc.ack.ackd_fast                | |
| ipc.ack.ack.ackd                     | |
| ipc.recv.bad_pkt_len             | |
| ipc.recv.bad_reply_len           | |
| ipc.recv.no_waiter               | |
| ipc.recv.copy_failed             | |
| ipc.kauth.vnode.mask             | |
| ipc.kauth.vnode.read             | |
| ipc.kauth.vnode.write            | |
| ipc.kauth.vnode.exec             | |
| ipc.kauth.vnode.del              | |
| ipc.kauth.vnode.read_attr        | |
| ipc.kauth.vnode.write_attr       | |
| ipc.kauth.vnode.read_ex_attr     | |
| ipc.kauth.vnode.write_ex_attr    | |
| ipc.kauth.vnode.read_sec         | |
| ipc.kauth.vnode.write_sec        | |
| ipc.kauth.vnode.take_own         | |
| ipc.kauth.vnode.link             | |
| ipc.kauth.vnode.create           | |
| ipc.kauth.vnode.move             | |
| ipc.kauth.vnode.mount            | |
| ipc.kauth.vnode.denied           | |
| ipc.kauth.vnode.ackd_before_deadline | |
| ipc.kauth.vnode.missed_deadline  | |
| ipc.kauth.file_op.mask           | |
| ipc.kauth_file_op.open           | |
| ipc.kauth.file_op.close          | |
| ipc.kauth.file_op.close_modified | |
| ipc.kauth.file_op.move           | |
| ipc.kauth.file_op.link           | |
| ipc.kauth.file_op.exec           | |
| ipc.kauth.file_op.remove         | |
| ipc.kauth.file_op.unmount        | |
| ipc.kauth.file_op.vork           | |
| ipc.kauth.file_op.create         | |

## <a name="resources"></a>Resources

- [Privacy bij Microsoft](https://privacy.microsoft.com/)
