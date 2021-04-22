---
title: Bronnen voor Microsoft Defender voor Eindpunt op Mac
description: Bronnen voor Microsoft Defender voor Eindpunt op Mac, waaronder hoe u het verwijdert, hoe u diagnostische logboeken, CLI-opdrachten en bekende problemen met het product verzamelt.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 34feeec0f8c34748678862b9aa7b20f84087eb5e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934523"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a>Resources voor Microsoft Defender voor Eindpunt op macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a>Diagnostische gegevens verzamelen

Als u een probleem kunt reproduceren, kunt u het logboekregistratieniveau verhogen, het systeem enige tijd uitvoeren en het logboekregistratieniveau herstellen naar het standaardniveau.

1. Het logboekregistratieniveau verhogen:

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. Het probleem reproduceren

3. Voer `sudo mdatp diagnostic create` een back-up van de Logboeken van Microsoft Defender voor Eindpunt uit. De bestanden worden opgeslagen in een ZIP-archief. Met deze opdracht wordt ook het bestandspad naar de back-up afgedrukt nadat de bewerking is geslaagd.

   > [!TIP]
   > Diagnostische logboeken worden standaard opgeslagen in `/Library/Application Support/Microsoft/Defender/wdavdiag/` . Als u de adreslijst wilt wijzigen waarin diagnostische logboeken worden opgeslagen, gaat u naar de onderstaande `--path [directory]` opdracht en vervangt u deze door de `[directory]` gewenste adreslijst.

   ```bash
   sudo mdatp diagnostic create
   ```
   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. Logboekregistratieniveau herstellen:

   ```bash
   mdatp log level set --level info
   ```
   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a>Installatieproblemen met logboekregistratie

Als er een fout optreedt tijdens de installatie, meldt het installatieprogramma alleen een algemene fout.

Het gedetailleerde logboek wordt opgeslagen in `/Library/Logs/Microsoft/mdatp/install.log` . Als u problemen ervaart tijdens de installatie, stuurt u ons dit bestand zodat we de oorzaak kunnen helpen opsporen.

## <a name="uninstalling"></a>Verwijderen

Er zijn verschillende manieren om Microsoft Defender voor Eindpunt op macOS te verwijderen. Hoewel centraal beheerd verwijderen beschikbaar is op JAMF, is deze nog niet beschikbaar voor Microsoft Intune.

### <a name="interactive-uninstallation"></a>Interactief verwijderen

- Open **Finder > Applications**. Klik met de rechtermuisknop **op Microsoft Defender voor Eindpunt > Naar prullenbak gaan.**

### <a name="from-the-command-line"></a>Vanuit de opdrachtregel

- ```sudo rm -rf '/Applications/Microsoft Defender ATP.app'```
- ```sudo rm -rf '/Library/Application Support/Microsoft/Defender/'```

## <a name="configuring-from-the-command-line"></a>Configureren vanaf de opdrachtregel

Belangrijke taken, zoals het beheren van productinstellingen en het activeren van scans op aanvraag, kunnen worden uitgevoerd vanaf de opdrachtregel:

|Groep        |Scenario                                   |Opdracht                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|Configuratie|Realtimebeveiliging in- of uitschakelen           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|Configuratie|Cloudbeveiliging in-/uitschakelen               |`mdatp config cloud --value [enabled/disabled]`                                   |
|Configuratie|Productdiagnose in- of uitschakelen            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|Configuratie|Automatische voorbeeldinzending in- of uitschakelen    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|Configuratie|Een bedreigingsnaam toevoegen aan de toegestane lijst      |`mdatp threat allowed add --name [threat-name]`                                   |
|Configuratie|Een bedreigingsnaam verwijderen uit de toegestane lijst |`mdatp threat allowed remove --name [threat-name]`                                |
|Configuratie|Alle toegestane bedreigingsnamen op een lijst zetten              |`mdatp threat allowed list`                                                       |
|Configuratie|PUA-beveiliging in- en uit-                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|Configuratie|PUA-beveiliging uitschakelen                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|Configuratie|Auditmodus inschakelen voor PUA-beveiliging      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|Configuratie|PassiveMode in-/uitschakelen                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|Diagnostische gegevens  |Het logboekniveau wijzigen                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|Diagnostische gegevens  |Diagnostische logboeken genereren                   |`mdatp diagnostic create --path [directory]`                                      |
|Gezondheid       |De status van het product controleren                 |`mdatp health`                                                                    |
|Gezondheid       |Controleren op een spefic-productkenmerk       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|Beveiliging   |Een pad scannen                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|Beveiliging   |Een snelle scan uitvoeren                            |`mdatp scan quick`                                                                |
|Beveiliging   |Een volledige scan uitvoeren                             |`mdatp scan full`                                                                 |
|Beveiliging   |Een lopende scan op aanvraag annuleren           |`mdatp scan cancel`                                                               |
|Beveiliging   |Een beveiligingsintelligentie-update aanvragen     |`mdatp definitions update`                                                        |
|EDR          |Groepslabel toevoegen aan apparaat. EDR-tags worden gebruikt voor het beheren van apparaatgroepen. Ga voor meer informatie naar https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups |`mdatp edr tag set --name GROUP --value [name]` |
|EDR          |Groepslabel van apparaat verwijderen               |`mdatp edr tag remove --tag-name [name]`                                          |
|EDR          |Groeps-id toevoegen                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a>Automatisch aanvullen inschakelen

Als u automatisch aanvullen in bash wilt inschakelen, voer u de volgende opdracht uit en start u de Terminal-sessie opnieuw:

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

Automatisch aanvullen inschakelen in zsh:

- Controleer of automatisch aanvullen is ingeschakeld op uw apparaat:

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- Als de vorige opdracht geen uitvoer produceert, kunt u automatisch aanvullen inschakelen met de volgende opdracht:

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- Voer de volgende opdrachten uit om automatisch aanvullen voor Microsoft Defender voor Eindpunt in macOS in te stellen en start de Terminal-sessie opnieuw:

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a>Client Microsoft Defender voor endpoint quarantine directory

`/Library/Application Support/Microsoft/Defender/quarantine/` bevat de bestanden die in quarantaine zijn geplaatst door `mdatp` . De bestanden zijn genoemd naar de bedreigingstrackingId. De huidige trackingIds wordt weergegeven met `mdatp threat list` .

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Microsoft Defender voor endpoint-portalgegevens

[De EDR-mogelijkheden](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)voor macOS zijn nu aangekomen op de Microsoft Defender voor Eindpunt-blog en bieden gedetailleerde richtlijnen voor wat u kunt verwachten in het Microsoft Defender for Endpoint Security Center.
