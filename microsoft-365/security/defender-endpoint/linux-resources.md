---
title: Microsoft Defender ATP voor Linux-resources
ms.reviewer: ''
description: Beschrijft bronnen voor Microsoft Defender ATP voor Linux, waaronder hoe u deze verwijdert, hoe u diagnostische logboeken, CLI-opdrachten en bekende problemen met het product verzamelt.
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7196053ffef3dffc3c737d0df26a5d12bdfe8a4c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187755"
---
# <a name="resources"></a>Resources

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a>Diagnostische gegevens verzamelen

Als u een probleem kunt reproduceren, moet u eerst het logboekregistratieniveau verhogen, het systeem enige tijd uitvoeren en vervolgens het logboekregistratieniveau herstellen naar het standaardniveau.

1. Het logboekregistratieniveau verhogen:

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. Reproduceer het probleem.

3. Voer de volgende opdracht uit om een back-up te maken van de logboeken van Defender voor eindpunten. De bestanden worden opgeslagen in een ZIP-archief.

   ```bash
   sudo mdatp diagnostic create
   ```

    Met deze opdracht wordt ook het bestandspad naar de back-up afgedrukt nadat de bewerking is geslaagd:

   ```Output
   Diagnostic file created: <path to file>
   ```

4. Logboekregistratieniveau herstellen:

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a>Problemen met de installatie van logboeken

Als er een fout optreedt tijdens de installatie, meldt het installatieprogramma alleen een algemene fout.

Het gedetailleerde logboek wordt opgeslagen in `/var/log/microsoft/mdatp_install.log` . Als u problemen ervaart tijdens de installatie, stuurt u ons dit bestand zodat we de oorzaak kunnen helpen opsporen.

## <a name="uninstall"></a>Verwijderen

Er zijn verschillende manieren om Defender voor Endpoint voor Linux te verwijderen. Als u een configuratiehulpmiddel zoals Poppenkast gebruikt, volgt u de instructies voor het verwijderen van het pakket voor het configuratieprogramma.

### <a name="manual-uninstallation"></a>Handmatig verwijderen

- `sudo yum remove mdatp` voor RHEL en varianten(CentOS en Oracle Linux).
- `sudo zypper remove mdatp` voor SLES en varianten.
- `sudo apt-get purge mdatp` voor Ubuntu- en Debian-systemen.

## <a name="configure-from-the-command-line"></a>Configureren vanaf de opdrachtregel

Belangrijke taken, zoals het beheren van productinstellingen en het activeren van scans op aanvraag, kunnen worden uitgevoerd vanaf de opdrachtregel.

### <a name="global-options"></a>Algemene opties

Standaard wordt met het opdrachtregelhulpmiddel het resultaat uitgevoerd in een door de mens gelezen indeling. Daarnaast ondersteunt het hulpprogramma ook de uitvoer van het resultaat als JSON, wat handig is voor automatiseringsscenario's. Als u de uitvoer wilt wijzigen in JSON, gaat u `--output json` naar een van de onderstaande opdrachten.

### <a name="supported-commands"></a>Ondersteunde opdrachten

De volgende tabel bevat opdrachten voor enkele van de meest voorkomende scenario's. Voer `mdatp help` de terminal uit om de volledige lijst met ondersteunde opdrachten weer te geven.

|Groep                 |Scenario                                                |Opdracht                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|Configuratie         |Realtimebeveiliging in- of uitschakelen                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|Configuratie         |Cloudbeveiliging in-/uitschakelen                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|Configuratie         |Productdiagnose in- of uitschakelen                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|Configuratie         |Automatische voorbeeldinzending in- of uitschakelen                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|Configuratie         |Passieve AV-modus in- of uitschakelen                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|Configuratie         |Een antivirusuitsluiting toevoegen/verwijderen voor een bestandsextensie  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|Configuratie         |Een antivirusuitsluiting voor een bestand toevoegen/verwijderen            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|Configuratie         |Een antivirusuitsluiting voor een adreslijst toevoegen/verwijderen       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|Configuratie         |Een antivirusuitsluiting toevoegen/verwijderen voor een proces         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|Configuratie         |Alle antivirusuitsluitingen op een lijst zetten                           |`mdatp exclusion list`                                                 |
|Configuratie         |Een bedreigingsnaam toevoegen aan de toegestane lijst                   |`mdatp threat allowed add --name [threat-name]`                        |
|Configuratie         |Een bedreigingsnaam verwijderen uit de toegestane lijst              |`mdatp threat allowed remove --name [threat-name]`                     |
|Configuratie         |Alle toegestane bedreigingsnamen op een lijst zetten                           |`mdatp threat allowed list`                                            |
|Configuratie         |PUA-beveiliging in- en uit-                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|Configuratie         |PUA-beveiliging uitschakelen                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|Configuratie         |Auditmodus inschakelen voor PUA-beveiliging                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|Diagnostische gegevens           |Het logboekniveau wijzigen                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|Diagnostische gegevens           |Diagnostische logboeken genereren                                |`mdatp diagnostic create --path [directory]`                           |
|Gezondheid                |De status van het product controleren                              |`mdatp health`                                                         |
|Beveiliging            |Een pad scannen                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|Beveiliging            |Een snelle scan uitvoeren                                         |`mdatp scan quick`                                                     |
|Beveiliging            |Een volledige scan uitvoeren                                          |`mdatp scan full`                                                      |
|Beveiliging            |Een lopende scan op aanvraag annuleren                        |`mdatp scan cancel`                                                    |
|Beveiliging            |Een beveiligingsintelligentie-update aanvragen                  |`mdatp definitions update`                                             |
|Beveiligingsgeschiedenis    |De volledige beveiligingsgeschiedenis afdrukken                       |`mdatp threat list`                                                    |
|Beveiligingsgeschiedenis    |Bedreigingsdetails krijgen                                      |`mdatp threat get --id [threat-id]`                                    |
|Quarantainebeheer |Alle in quarantaine geplaatste bestanden op een lijst zetten                              |`mdatp threat quarantine list`                                         |
|Quarantainebeheer |Alle bestanden uit de quarantaine verwijderen                    |`mdatp threat quarantine remove-all`                                   |
|Quarantainebeheer |Een bestand toevoegen dat is gedetecteerd als een bedreiging voor de quarantaine       |`mdatp threat quarantine add --id [threat-id]`                         |
|Quarantainebeheer |Een bestand verwijderen dat is gedetecteerd als een bedreiging uit de quarantaine  |`mdatp threat quarantine remove --id [threat-id]`                      |
|Quarantainebeheer |Een bestand uit de quarantaine herstellen                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|Eindpuntdetectie en -antwoord |Vroege preview instellen (ongebruikt)                    |`mdatp edr early-preview [enable|disable]`                             |
|Eindpuntdetectie en -antwoord |Groeps-id instellen                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|Eindpuntdetectie en -antwoord |Tag instellen/verwijderen, alleen `GROUP` ondersteund        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|Eindpuntdetectie en -antwoord |lijstuitsluitingen (hoofd)                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Microsoft Defender voor endpoint-portalgegevens

In de portal Defender voor eindpunt ziet u twee categorieën met informatie:

- Antiviruswaarschuwingen, waaronder:
  - Ernst
  - Scantype
  - Apparaatgegevens (hostnaam, apparaataanduiding, tenant-id, app-versie en ostype)
  - Bestandsgegevens (naam, pad, grootte en hash)
  - Bedreigingsgegevens (naam, type en status)
- Apparaatgegevens, waaronder:
  - Apparaataanduiding
  - Tenant-id
  - App-versie
  - Hostname
  - OS-type
  - OS-versie
  - Computermodel
  - Processorarchitectuur
  - Of het apparaat een virtuele machine is

### <a name="known-issues"></a>Bekende problemen

- Mogelijk ziet u 'Geen sensorgegevens, communicatie met verminderde werking' op de pagina met computergegevens van de portal van het Microsoft Defender-beveiligingscentrum, ook al werkt het product zoals verwacht. We werken aan een oplossing voor dit probleem.
- Aangemelde gebruikers worden niet weergegeven in de microsoft Defender-beveiligingscentrumportal.
- Als de installatie van *libatomic1* mislukt in SUSE-distributies, moet u controleren of uw besturingssysteem is geregistreerd:

   ```bash
   sudo SUSEConnect --status-text
   ```
