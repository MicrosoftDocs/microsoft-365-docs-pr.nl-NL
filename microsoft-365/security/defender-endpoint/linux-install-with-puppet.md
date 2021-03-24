---
title: Microsoft Defender ATP voor Linux implementeren met Puppet
ms.reviewer: ''
description: Hier wordt beschreven hoe u Microsoft Defender ATP voor Linux implementeert met Behulp van Poppenspel.
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
ms.openlocfilehash: 06611c19994ba34c4b59eb1a32b9ab9fd91cc1aa
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059717"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-linux-with-puppet"></a>Microsoft Defender voor eindpunt voor Linux implementeren met Puppet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

In dit artikel wordt beschreven hoe u Defender voor Eindpunt voor Linux implementeert met Behulp van Poppenspel. Voor een geslaagde implementatie moeten alle volgende taken zijn voltooid:

- [Het onboarding-pakket downloaden](#download-the-onboarding-package)
- [Poppopmanifest maken](#create-a-puppet-manifest)
- [Implementatie](#deployment)
- [Onboarding-status controleren](#check-onboarding-status)

## <a name="prerequisites-and-system-requirements"></a>Vereisten en systeemvereisten

 Zie de hoofdpagina van Defender voor Eindpunt voor Linux voor een beschrijving van vereisten en systeemvereisten voor de huidige [softwareversie.](microsoft-defender-endpoint-linux.md)

Daarnaast moet u voor de implementatie van Poppenspel bekend zijn met beheertaken van Poppenkast, Dat Popping is geconfigureerd en weet hoe u pakketten implementeert. Poppop heeft veel manieren om dezelfde taak uit te voeren. Deze instructies gaan uit van de beschikbaarheid van ondersteunde Poppopmodules, zoals *geschikt voor* het implementeren van het pakket. Uw organisatie kan een andere werkstroom gebruiken. Raadpleeg de [documentatie van De Poppop](https://puppet.com/docs) voor meer informatie.

## <a name="download-the-onboarding-package"></a>Het onboarding-pakket downloaden

Download het onboarding-pakket van het Microsoft Defender-beveiligingscentrum:

1. Ga in het Microsoft Defender-beveiligingscentrum naar **Instellingen > Apparaatbeheer > Onboarding.**
2. Selecteer in de eerste vervolgkeuzelijst **Linux Server** als besturingssysteem. Selecteer in de tweede vervolgkeuzelijst **Uw voorkeursprogramma** voor configuratiebeheer voor Linux als implementatiemethode.
3. Selecteer **Onboarding-pakket downloaden.** Sla het bestand op als WindowsDefenderATPOnboardingPackage.zip.

    ![Schermafbeelding van het Microsoft Defender-beveiligingscentrum](images/atp-portal-onboarding-linux-2.png)

4. Controleer in een opdrachtprompt of u het bestand hebt. 

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
5. Haal de inhoud van het archief op.
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-a-puppet-manifest"></a>Een pop-popmanifest maken

U moet een Poppopmanifest maken voor het implementeren van Defender voor Eindpunt voor Linux op apparaten die worden beheerd door een Poppopserver. In dit voorbeeld wordt gebruik gemaakt van de *apt-* en *yumrepo-modules* die beschikbaar zijn via poppoplabs en wordt ervan uitgenomen dat de modules zijn geïnstalleerd op de Server van De Poppop.

Maak de mappen *install_mdatp/bestanden* en *install_mdatp/manifesten* onder de modulesmap van de installatie van Uw Poppenkast. Deze map bevindt zich meestal in */etc/poppenkast/code/omgevingen/productie/modules* op uw Poppenspelserver. Kopieer de mdatp_onboard.jsbestand dat hierboven is gemaakt *naar de map install_mdatp/bestanden.* Een *init.pp maken* bestand met de implementatie-instructies:

```bash
pwd
```
```Output
/etc/puppetlabs/code/environments/production/modules
```

```bash
tree install_mdatp
```
```Output
install_mdatp
├── files
│   └── mdatp_onboard.json
└── manifests
    └── init.pp
```

### <a name="contents-of-install_mdatpmanifestsinitpp"></a>Inhoud van `install_mdatp/manifests/init.pp`

Defender voor Eindpunt voor Linux kan worden geïmplementeerd via een van de volgende kanalen (hieronder aangeduid als *[kanaal]*): *insiders-fast,* *insiders-slow* of *prod*. Elk van deze kanalen komt overeen met een Linux-softwareopslagplaats.

De keuze van het kanaal bepaalt het type en de frequentie van de updates die op uw apparaat worden aangeboden. Apparaten in *insiders-fast* zijn de eersten die updates en nieuwe functies ontvangen, later gevolgd door *insiders-slow* en ten laatste *door prod*.

Als u een voorbeeld van nieuwe functies wilt bekijken en vroegtijdig feedback wilt geven, wordt u aangeraden sommige apparaten in uw bedrijf te configureren om *insiders-fast* of *insiders-slow te gebruiken.*

> [!WARNING]
> Als u het kanaal na de eerste installatie overschakelt, moet het product opnieuw worden geïnstalleerd. Als u het productkanaal wilt wijzigen: verwijder het bestaande pakket, configureer het apparaat opnieuw om het nieuwe kanaal te gebruiken en volg de stappen in dit document om het pakket vanaf de nieuwe locatie te installeren.

Noteer uw distributie en versie en identificeer de dichtstbijzijnde vermelding voor de versie onder `https://packages.microsoft.com/config/` .

Vervang *[distro]* en *[versie]* in de onderstaande opdrachten door de gegevens die u hebt geïdentificeerd:

> [!NOTE]
> In het geval van RedHat, Oracle EL en CentOS 8 vervangt *u [distro] door* 'rhel'.

```puppet
# Puppet manifest to install Microsoft Defender ATP.
# @param channel The release channel based on your environment, insider-fast or prod.
# @param distro The Linux distribution in lowercase. In case of RedHat, Oracle EL, and CentOS 8, the distro variable should be 'rhel'.
# @param version The Linux distribution release number, e.g. 7.4.

class install_mdatp (
$channel = 'insiders-fast',
$distro = undef,
$version = undef
){
    case $::osfamily {
        'Debian' : {
            apt::source { 'microsoftpackages' :
                location => "https://packages.microsoft.com/${distro}/${version}/prod",
                release  => $channel,
                repos    => 'main',
                key      => {
                    'id'     => 'BC528686B50D79E339D3721CEB3E94ADBE1229CF',
                    'server' => 'keyserver.ubuntu.com',
                },
            }
        }
        'RedHat' : {
            yumrepo { 'microsoftpackages' :
                baseurl  => "https://packages.microsoft.com/${distro}/${version}/${channel}",
                descr    => "packages-microsoft-com-prod-${channel}",
                enabled  => 1,
                gpgcheck => 1,
                gpgkey   => 'https://packages.microsoft.com/keys/microsoft.asc'
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }

    case $::osfamily {
        /(Debian|RedHat)/: {
            file { ['/etc/opt', '/etc/opt/microsoft', '/etc/opt/microsoft/mdatp']:
                ensure => directory,
                owner  => root,
                group  => root,
                mode   => '0755'
            }

            file { '/etc/opt/microsoft/mdatp/mdatp_onboard.json':
                source  => 'puppet:///modules/install_mdatp/mdatp_onboard.json',
                owner   => root,
                group   => root,
                mode    => '0600',
                require => File['/etc/opt/microsoft/mdatp']
            }

            package { 'mdatp':
                ensure  => 'installed',
                require => File['/etc/opt/microsoft/mdatp/mdatp_onboard.json']
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }
}
```

## <a name="deployment"></a>Implementatie

Neem het bovenstaande manifest op in uw site.pp bestand:

```bash
cat /etc/puppetlabs/code/environments/production/manifests/site.pp
```
```Output
node "default" {
    include install_mdatp
}
```

Geregistreerde agentapparaten peilen regelmatig de Server van De Poppop en installeren nieuwe configuratieprofielen en beleid zodra ze worden gedetecteerd.

## <a name="monitor-puppet-deployment"></a>Implementatie van Poppop controleren

Op het agentapparaat kunt u ook de onboarding-status controleren door het volgende uit te werken:

```bash
mdatp health
```
```Output
...
licensed                                : true
org_id                                  : "[your organization identifier]"
...
```

- **licentie:** Hiermee wordt bevestigd dat het apparaat is gekoppeld aan uw organisatie.

- **orgId:** dit is de id van de Defender voor endpoint-organisatie.

## <a name="check-onboarding-status"></a>Onboarding-status controleren

U kunt controleren of apparaten correct zijn onboarded door een script te maken. In het volgende script worden bijvoorbeeld geregistreerde apparaten gecontroleerd op de onboarding-status:

```bash
mdatp health --field healthy
```

De bovenstaande opdracht wordt `1` afgedrukt als het product is onboarded en werkt zoals verwacht.

> [!IMPORTANT]
> Wanneer het product voor het eerst wordt gestart, worden de meest recente antimalwaredefinities gedownload. Afhankelijk van uw internetverbinding kan dit enkele minuten duren. Gedurende deze periode retourneert de bovenstaande opdracht een waarde van `0` .

Als het product niet gezond is, geeft de exitcode (die kan worden `echo $?` gecontroleerd) het probleem aan:

- 1 als het apparaat nog niet is onboarded.
- 3 als de verbinding met de daemon niet kan worden vastgesteld.

## <a name="log-installation-issues"></a>Problemen met de installatie van logboeken

 Zie Installatieproblemen met logboeken voor meer informatie over het vinden van het automatisch gegenereerde logboek dat door het installatieprogramma is gemaakt wanneer er een fout [optreedt.](linux-resources.md#log-installation-issues)

## <a name="operating-system-upgrades"></a>Upgrades van besturingssysteem

Wanneer u een upgrade van uw besturingssysteem naar een nieuwe hoofdversie hebt uitgevoerd, moet u Eerst Defender voor Eindpunt voor Linux verwijderen, de upgrade installeren en ten slotte Defender voor Eindpunt voor Linux opnieuw configureren op uw apparaat.

## <a name="uninstallation"></a>Verwijderen

Maak een module *remove_mdatp* vergelijkbaar met *install_mdatp* met de volgende inhoud in *init.pp* bestand:

```bash
class remove_mdatp {
    package { 'mdatp':
        ensure => 'purged',
    }
}
```
