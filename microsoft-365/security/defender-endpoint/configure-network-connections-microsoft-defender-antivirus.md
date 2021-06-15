---
title: Netwerkverbindingen van Microsoft Defender Antivirus configureren en valideren
description: Configureer en test uw verbinding met de Microsoft Defender Antivirus cloudbeveiligingsservice.
keywords: antivirus, Microsoft Defender Antivirus, antimalware, beveiliging, defender, cloud, agressiviteit, beschermingsniveau
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 1fc0f76ece240c9d7efc92680c34b0477141f52b
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925137"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Netwerkverbindingen van Microsoft Defender Antivirus configureren en valideren

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Als u Microsoft Defender Antivirus beveiliging in de cloud correct wilt laten werken, moet uw beveiligingsteam uw netwerk zo configureren dat verbindingen tussen uw eindpunten en bepaalde Microsoft-servers worden toegestaan. In dit artikel worden de verbindingen vermeld die moeten worden toegestaan, bijvoorbeeld met behulp van firewallregels, en worden instructies gegeven voor het valideren van uw verbinding. Als u uw beveiliging correct configureert, kunt u ervoor zorgen dat u de beste waarde ontvangt van uw beveiligingsservices die in de cloud worden geleverd.

Zie het blogbericht [Belangrijke wijzigingen in het eindpunt van Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) voor meer informatie over netwerkconnectiviteit.

> [!TIP]
> Ga naar de demowebsite van Microsoft Defender voor Eindpunt demo.wd.microsoft.com [om](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) te bevestigen dat de volgende functies werken:
>
> - Cloudbeveiliging
> - Snel leren (inclusief blok op het eerste gezicht)
> - Mogelijk ongewenste blokkering van toepassingen

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Verbindingen met de Microsoft Defender Antivirus cloudservice toestaan

De Microsoft Defender Antivirus cloudservice biedt snelle, sterke beveiliging voor uw eindpunten. Het inschakelen van de door de cloud geleverde beveiligingsservice is optioneel, maar het wordt ten zeerste aanbevolen omdat deze belangrijke bescherming biedt tegen malware op uw eindpunten en in uw netwerk. Zie [Beveiliging in de cloud](enable-cloud-protection-microsoft-defender-antivirus.md) inschakelen voor meer informatie over het inschakelen van de service met Intune, Microsoft Endpoint Configuration Manager, Groepsbeleid, PowerShell-cmdlets of op afzonderlijke clients in de Windows-beveiliging app. 

Nadat u de service hebt ingeschakeld, moet u mogelijk uw netwerk of firewall configureren om verbindingen tussen de service en uw eindpunten toe te staan. Omdat uw beveiliging een cloudservice is, moeten computers toegang hebben tot internet en de Microsoft Defender voor Office 365 machine learning-services. Sluit de URL niet uit `*.blob.core.windows.net` van een netwerkcontrole. 

> [!NOTE]
> De Microsoft Defender Antivirus cloudservice is een mechanisme voor het leveren van bijgewerkte beveiliging voor uw netwerk en eindpunten. Hoewel het een cloudservice wordt genoemd, is het niet alleen beveiliging voor bestanden die zijn opgeslagen in de cloud, maar wordt gebruikgemaakt van gedistribueerde resources en machine learning om uw eindpunten te beschermen tegen een snelheid die veel sneller is dan traditionele beveiligingsinformatie-updates.

## <a name="services-and-urls"></a>Services en URL's

De tabel in deze sectie bevat de services en de bijbehorende websiteadressen (URL's). 

Zorg ervoor dat er geen firewall- of netwerkfilterregels zijn die toegang tot deze URL's weigeren. Anders moet u mogelijk een regel voor toestaan speciaal voor hen maken (met uitzondering van de `*.blob.core.windows.net` URL). De URL's in de volgende tabel gebruiken poort 443 voor communicatie.

| Service en beschrijving | URL |
|----|---- |
| Microsoft Defender Antivirus door de cloud geleverde beveiligingsservice, ook wel Microsoft Active Protection Service (KAARTEN)<p>Deze service wordt door Microsoft Defender Antivirus gebruikt om beveiliging in de cloud te bieden|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
| Microsoft Update Service (MU) en Windows Update Service (WU) <p>Deze services maken beveiligingsinformatie en productupdates mogelijk   |`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> Zie Verbindings eindpunten voor Windows [Update voor meer informatie](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|Beveiligingsinformatieupdates Alternatieve downloadlocatie (ADL)<p>Dit is een alternatieve locatie voor Microsoft Defender Antivirus beveiligingsinformatieupdates als de geïnstalleerde beveiligingsinformatie verouderd is (7 of meer dagen achter)|  `*.download.microsoft.com`  <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| Opslag voor malware indienen <p>Dit is de uploadlocatie voor bestanden die naar Microsoft zijn verzonden via het formulier Voorzending of automatische voorbeeldinzending | `ussus1eastprod.blob.core.windows.net` <p>    `ussus2eastprod.blob.core.windows.net` <p>    `ussus3eastprod.blob.core.windows.net` <p>    `ussus4eastprod.blob.core.windows.net` <p>    `wsus1eastprod.blob.core.windows.net` <p>    `wsus2eastprod.blob.core.windows.net` <p>    `ussus1westprod.blob.core.windows.net` <p>    `ussus2westprod.blob.core.windows.net` <p>    `ussus3westprod.blob.core.windows.net` <p>    `ussus4westprod.blob.core.windows.net` <p>    `wsus1westprod.blob.core.windows.net` <p>    `wsus2westprod.blob.core.windows.net` <p>    `usseu1northprod.blob.core.windows.net` <p>    `wseu1northprod.blob.core.windows.net` <p>    `usseu1westprod.blob.core.windows.net` <p>    `wseu1westprod.blob.core.windows.net` <p>    `ussuk1southprod.blob.core.windows.net` <p>    `wsuk1southprod.blob.core.windows.net` <p>    `ussuk1westprod.blob.core.windows.net` <p>    `wsuk1westprod.blob.core.windows.net` |
| Intrekkingslijst voor certificaten (CRL) <p>Deze lijst wordt gebruikt door Windows bij het maken van de SSL-verbinding met KAARTEN voor het bijwerken van de CRL   | `http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p>   `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs` |
| Symbol Store <p>Het symboolopslag wordt gebruikt door Microsoft Defender Antivirus om bepaalde kritieke bestanden te herstellen tijdens herstelstromen   | `https://msdl.microsoft.com/download/symbols` |
| Universele telemetrieclient <p>Deze client wordt gebruikt door Windows om diagnostische gegevens van de client te verzenden<p> Microsoft Defender Antivirus telemetrie gebruikt voor productkwaliteitscontroledoeleinden    | De update gebruikt SSL (TCP-poort 443) om manifesten te downloaden en diagnostische gegevens te uploaden naar Microsoft met de volgende DNS-eindpunten: <p> `vortex-win.data.microsoft.com` <p>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>Verbindingen tussen uw netwerk en de cloud valideren

Nadat u de url's hierboven hebt toestaan, kunt u testen of u verbinding hebt met de Microsoft Defender Antivirus-cloudservice en correct gegevens rapporteert en ontvangt om ervoor te zorgen dat u volledig bent beveiligd.

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a>Het cmdline-hulpprogramma gebruiken om beveiliging in de cloud te valideren

Gebruik het volgende argument met Microsoft Defender Antivirus command-line utility () om te controleren of uw netwerk kan communiceren met de `mpcmdrun.exe` Microsoft Defender Antivirus cloudservice:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> U moet een versie op beheerdersniveau van de opdrachtprompt openen. Klik met de rechtermuisknop op het item in het menu Start, klik op **Uitvoeren als beheerder** en klik op **Ja** bij de machtigingenprompt. Deze opdracht werkt alleen op Windows 10, versie 1703 of hoger.

Zie De Microsoft Defender Antivirus [beheren mpcmdrun.exe opdrachtregel](command-line-arguments-microsoft-defender-antivirus.md)voor meer informatie.

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a>Poging om een nep-malwarebestand van Microsoft te downloaden

U kunt een voorbeeldbestand downloaden dat Microsoft Defender Antivirus wordt gedetecteerd en geblokkeerd als u goed bent verbonden met de cloud.

Download het bestand door naar [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .

> [!NOTE]
> Dit bestand is geen echt stukje malware. Het is een nepbestand dat is ontworpen om te testen of u goed verbonden bent met de cloud.

Als u goed bent verbonden, ziet u een waarschuwing voor Microsoft Defender Antivirus melding.

Als u een Microsoft Edge gebruikt, ziet u ook een meldingsbericht:

![Microsoft Edge de gebruiker informeren dat malware is gevonden](images/defender/wdav-bafs-edge.png)

Een soortgelijk bericht treedt op als u Internet Explorer gebruikt:

![Microsoft Defender Antivirus de gebruiker te informeren dat malware is gevonden](images/defender/wdav-bafs-ie.png)

U ziet ook een detectie onder In quarantaine geplaatste **bedreigingen** in de sectie **Scangeschiedenis** in de Windows-beveiliging app:

1. Open de Windows-beveiliging app door op het schildpictogram op de taakbalk te klikken of door te zoeken in het startmenu voor **beveiliging.**

2. Selecteer **Virusbeveiliging & en** selecteer vervolgens **Beschermingsgeschiedenis.**

3. Selecteer onder **de sectie In quarantaine geplaatste** bedreigingen de optie Volledige geschiedenis **bekijken** om de gedetecteerde nep-malware te zien.

   > [!NOTE]
   > Versies van Windows 10 versie 1703 hebben een andere gebruikersinterface. Zie [Microsoft Defender Antivirus in de Windows-beveiliging app](microsoft-defender-security-center-antivirus.md).

   In Windows gebeurtenislogboek wordt ook Windows Defender [clientgebeurtenis-id 1116.](troubleshoot-microsoft-defender-antivirus.md)

