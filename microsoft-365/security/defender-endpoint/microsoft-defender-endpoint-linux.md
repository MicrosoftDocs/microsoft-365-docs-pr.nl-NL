---
title: Microsoft Defender ATP voor Linux
ms.reviewer: ''
description: Hier wordt beschreven hoe u Microsoft Defender ATP voor Linux installeert en gebruikt.
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
ms.openlocfilehash: ce7b15a727ddfa9b0d2bc68b7901f2e79aaf0721
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058742"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a>Microsoft Defender voor Eindpunt voor Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

In dit onderwerp wordt beschreven hoe u Microsoft Defender voor Eindpunt voor Linux kunt installeren, configureren, bijwerken en gebruiken.

> [!CAUTION]
> Het uitvoeren van andere endpointbeveiligingsproducten van derden naast Microsoft Defender voor Eindpunt voor Linux kan waarschijnlijk prestatieproblemen en onvoorspelbare systeemfouten veroorzaken.

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a>Microsoft Defender voor Eindpunt voor Linux installeren

### <a name="prerequisites"></a>Vereisten

- Toegang tot de microsoft Defender-beveiligingscentrumportal
- Linux-distributie met [de systemd](https://systemd.io/) system manager
- Beginnerservaring in Linux- en BASH-scripting
- Beheerdersbevoegdheden op het apparaat (in geval van handmatige implementatie)

### <a name="installation-instructions"></a>Installatie-instructies

Er zijn verschillende methoden en implementatiehulpmiddelen waarmee u Microsoft Defender voor Eindpunt voor Linux kunt installeren en configureren.

Over het algemeen moet u de volgende stappen ondernemen:

- Zorg ervoor dat u een Microsoft Defender voor Eindpunt-abonnement hebt en dat u toegang hebt tot de [Microsoft Defender for Endpoint-portal.](microsoft-defender-security-center.md)
- Microsoft Defender voor Eindpunt voor Linux implementeren met behulp van een van de volgende implementatiemethoden:
  - Het opdrachtregelhulpmiddel:
    - [Handmatige implementatie](linux-install-manually.md)
  - Beheerhulpmiddelen van derden:
    - [Implementeren met behulp van Het configuratiebeheerprogramma van De pop-over](linux-install-with-puppet.md)
    - [Implementeren met behulp van het hulpprogramma voor configuratiebeheer van Ansible](linux-install-with-ansible.md)

Als er installatiefouten optreden, raadpleegt u [Installatiefouten oplossen in Microsoft Defender voor Eindpunt voor Linux.](linux-support-install.md)

### <a name="system-requirements"></a>Systeemvereisten

- Ondersteunde Linux-serverdistributies en -versies:

  - Red Hat Enterprise Linux 7.2 of hoger
  - CentOS 7.2 of hoger
  - Ubuntu 16.04 LTS of hoger LTS
  - Debian 9 of hoger
  - SUSE Linux Enterprise Server 12 of hoger
  - Oracle Linux 7.2 of hoger

- Minimum kernel versie 3.10.0-327
- De `fanotify` kerneloptie moet zijn ingeschakeld
  > [!CAUTION]
  > Het uitvoeren van Defender voor Eindpunt voor Linux naast andere op basis van `fanotify` beveiligingsoplossingen wordt niet ondersteund. Dit kan leiden tot onvoorspelbare resultaten, waaronder het ophangen van het besturingssysteem.

- Schijfruimte: 1 GB
- De oplossing biedt momenteel realtime bescherming voor de volgende bestandssysteemtypen:

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

Nadat u de service hebt ingeschakeld, moet u mogelijk uw netwerk of firewall configureren om uitgaande verbindingen tussen de service en uw eindpunten toe te staan.

- Audit framework ( `auditd` ) moet zijn ingeschakeld.
  >[!NOTE]
  > Systeemgebeurtenissen die zijn vastgelegd met regels die zijn toegevoegd, worden toegevoegd aan auditlogboeken en kunnen van invloed zijn op de controle van de `audit.logs` host en de upstreamverzameling. Gebeurtenissen die zijn toegevoegd door Microsoft Defender voor Endopoint voor Linux, worden met de sleutel `mdatp` gemarkeerd.

### <a name="network-connections"></a>Netwerkverbindingen

In de volgende downloadbare spreadsheet vindt u de services en bijbehorende URL's waar uw netwerk verbinding mee moet kunnen maken. U moet ervoor zorgen dat er geen firewall- of netwerkfilterregels zijn die de toegang tot deze URL's weigeren. Als dat zo is, moet u mogelijk een *regel* voor toestaan speciaal voor hen maken.

|**Spreadsheet met domeinenlijst**|**Beschrijving**|
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLLs spreadsheet](images/mdatp-urls.png)<br/>  | Spreadsheet met specifieke DNS-records voor servicelocaties, geografische locaties en besturingssysteem. <br><br>[Download de spreadsheet hier.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> Zie Proxy- en internetverbindingsinstellingen configureren voor een specifiekere [URL-lijst.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)

Defender voor Eindpunt kan een proxyserver ontdekken met behulp van de volgende detectiemethoden:
- Transparante proxy
- Handmatige statische proxyconfiguratie

Als een proxy of firewall anoniem verkeer blokkeert, moet u ervoor zorgen dat anoniem verkeer is toegestaan in de eerder genoemde URL's. Voor doorzichtige proxies is er geen extra configuratie nodig voor Defender voor Eindpunt. Voor statische proxy volgt u de stappen in [Handmatige statische proxyconfiguratie.](linux-static-proxy-configuration.md)

> [!WARNING]
> PAC-, WPAD- en geverifieerde proxies worden niet ondersteund. Zorg ervoor dat alleen een statische proxy of transparante proxy wordt gebruikt.
>
> SSL-inspectie en het onderscheppen van proxies worden ook niet ondersteund om beveiligingsredenen. Configureer een uitzondering voor SSL-inspectie en uw proxyserver om gegevens van Defender voor Endpoint voor Linux rechtstreeks door te geven aan de relevante URL's zonder interceptie. Als u uw interceptiecertificaat toevoegt aan de algemene winkel, is onderschepping niet toegestaan.

Zie Problemen met cloudconnectiviteit oplossen voor Microsoft Defender voor Eindpunt voor Linux voor meer informatie over het oplossen van problemen met [de cloud.](linux-support-connectivity.md)

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a>Microsoft Defender voor Eindpunt voor Linux bijwerken

Microsoft publiceert regelmatig software-updates om de prestaties, beveiliging en nieuwe functies te verbeteren. Als u Microsoft Defender voor Eindpunt voor Linux wilt bijwerken, raadpleegt u Updates implementeren voor [Microsoft Defender voor Eindpunt voor Linux.](linux-updates.md)

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a>Microsoft Defender configureren voor Eindpunt voor Linux

Richtlijnen voor het configureren van het product in bedrijfsomgevingen zijn beschikbaar in [Set preferences for Microsoft Defender for Endpoint for Linux](linux-preferences.md).

## <a name="resources"></a>Resources

- Zie Resources voor meer informatie over logboekregistratie, verwijderen of andere [onderwerpen.](linux-resources.md)
