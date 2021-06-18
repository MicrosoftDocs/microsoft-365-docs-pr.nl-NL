---
title: Netwerkverbindingen van Microsoft Defender Antivirus configureren en valideren
description: Configureer en test uw verbinding met de cloudbeveiligingsservice van Microsoft Defender Antivirus.
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
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 6ccc2eb171e85793899a7862ed9a317815d89626
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007577"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Netwerkverbindingen van Microsoft Defender Antivirus configureren en valideren

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Uw beveiligingsteam moet uw netwerk zo configureren dat verbindingen tussen uw eindpunten en bepaalde Microsoft-servers worden toegestaan om ervoor te zorgen dat de beveiliging van Microsoft Defender Antivirus in de cloud correct werkt. In dit artikel worden de verbindingen vermeld die moeten worden toegestaan, bijvoorbeeld met behulp van firewallregels, en worden instructies gegeven voor het valideren van uw verbinding. Als u uw beveiliging correct configureert, kunt u ervoor zorgen dat u de beste waarde ontvangt van uw beveiligingsservices die in de cloud worden geleverd.

Zie het blogbericht [Belangrijke wijzigingen in het eindpunt van Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) voor meer informatie over netwerkconnectiviteit.

> [!TIP]
> Ga naar de demowebsite van Microsoft Defender voor Eindpunt demo.wd.microsoft.com [om](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) te bevestigen dat de volgende functies werken:
>
> - Cloudbeveiliging
> - Snel leren (inclusief blok op het eerste gezicht)
> - Mogelijk ongewenste blokkering van toepassingen

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Verbindingen met de Microsoft Defender Antivirus-cloudservice toestaan

De Microsoft Defender Antivirus-cloudservice biedt snelle, krachtige beveiliging voor uw eindpunten. Het inschakelen van de door de cloud geleverde beveiligingsservice is optioneel, maar het wordt ten zeerste aanbevolen omdat deze belangrijke bescherming biedt tegen malware op uw eindpunten en in uw netwerk. Zie Beveiliging in de cloud inschakelen voor meer informatie over het inschakelen van de service met Intune, Microsoft Endpoint Configuration Manager, Groepsbeleid, PowerShell-cmdlets of op afzonderlijke clients in de Windows [Security-app.](enable-cloud-protection-microsoft-defender-antivirus.md) 

Nadat u de service hebt ingeschakeld, moet u mogelijk uw netwerk of firewall configureren om verbindingen tussen de service en uw eindpunten toe te staan. Omdat uw beveiliging een cloudservice is, moeten computers toegang hebben tot internet en de Machine Learning-services van Microsoft Defender voor Office 365 bereiken. Sluit de URL niet uit `*.blob.core.windows.net` van een netwerkcontrole. 

> [!NOTE]
> De Microsoft Defender Antivirus-cloudservice is een mechanisme voor het leveren van bijgewerkte beveiliging aan uw netwerk en eindpunten. Hoewel het een cloudservice wordt genoemd, is het niet alleen beveiliging voor bestanden die zijn opgeslagen in de cloud, maar wordt gebruikgemaakt van gedistribueerde resources en machine learning om uw eindpunten te beschermen tegen een snelheid die veel sneller is dan traditionele beveiligingsinformatie-updates.

## <a name="services-and-urls"></a>Services en URL's

De tabel in deze sectie bevat de services en de bijbehorende websiteadressen (URL's). 

Zorg ervoor dat er geen firewall- of netwerkfilterregels zijn die toegang tot deze URL's weigeren. Anders moet u mogelijk een regel voor toestaan speciaal voor hen maken (met uitzondering van de `*.blob.core.windows.net` URL). De URL's in de volgende tabel gebruiken poort 443 voor communicatie.

| Service en beschrijving | URL |
|----|---- |
| Microsoft Defender Antivirus-beveiligingsservice in de cloud, ook wel Microsoft Active Protection Service (MAPS) genoemd<p>Deze service wordt door Microsoft Defender Antivirus gebruikt om beveiliging in de cloud te bieden|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
| Microsoft Update Service (MU) en Windows Update Service (WU) <p>Deze services maken beveiligingsinformatie en productupdates mogelijk   |`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> Zie Verbindings eindpunten [voor Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update) voor meer informatie|
|Beveiligingsinformatieupdates Alternatieve downloadlocatie (ADL)<p>Dit is een alternatieve locatie voor updates van Microsoft Defender Antivirus Security Intelligence als de geïnstalleerde beveiligingsintelligentie verouderd is (7 of meer dagen achter)|  `*.download.microsoft.com`  <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| Opslag voor malware indienen <p>Dit is de uploadlocatie voor bestanden die naar Microsoft zijn verzonden via het formulier Voorzending of automatische voorbeeldinzending | `ussus1eastprod.blob.core.windows.net` <p>    `ussus2eastprod.blob.core.windows.net` <p>    `ussus3eastprod.blob.core.windows.net` <p>    `ussus4eastprod.blob.core.windows.net` <p>    `wsus1eastprod.blob.core.windows.net` <p>    `wsus2eastprod.blob.core.windows.net` <p>    `ussus1westprod.blob.core.windows.net` <p>    `ussus2westprod.blob.core.windows.net` <p>    `ussus3westprod.blob.core.windows.net` <p>    `ussus4westprod.blob.core.windows.net` <p>    `wsus1westprod.blob.core.windows.net` <p>    `wsus2westprod.blob.core.windows.net` <p>    `usseu1northprod.blob.core.windows.net` <p>    `wseu1northprod.blob.core.windows.net` <p>    `usseu1westprod.blob.core.windows.net` <p>    `wseu1westprod.blob.core.windows.net` <p>    `ussuk1southprod.blob.core.windows.net` <p>    `wsuk1southprod.blob.core.windows.net` <p>    `ussuk1westprod.blob.core.windows.net` <p>    `wsuk1westprod.blob.core.windows.net` |
| Intrekkingslijst voor certificaten (CRL) <p>Deze lijst wordt door Windows gebruikt bij het maken van de SSL-verbinding met KAARTEN voor het bijwerken van de CRL   | `http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p>   `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs` |
| Symbol Store <p>De symboolopslag wordt door Microsoft Defender Antivirus gebruikt om bepaalde kritieke bestanden te herstellen tijdens herstelstromen   | `https://msdl.microsoft.com/download/symbols` |
| Universele telemetrieclient <p>Deze client wordt door Windows gebruikt om diagnostische gegevens van de client te verzenden<p> Microsoft Defender Antivirus gebruikt telemetrie voor kwaliteitsbewakingsdoeleinden    | De update gebruikt SSL (TCP-poort 443) om manifesten te downloaden en diagnostische gegevens te uploaden naar Microsoft met de volgende DNS-eindpunten: <p> `vortex-win.data.microsoft.com` <p>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>Verbindingen tussen uw netwerk en de cloud valideren

Nadat u de hierboven genoemde URL's hebt toestaan, kunt u testen of u verbinding hebt met de Microsoft Defender Antivirus-cloudservice en correct gegevens rapporteert en ontvangt om ervoor te zorgen dat u volledig bent beveiligd.

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a>Het cmdline-hulpprogramma gebruiken om beveiliging in de cloud te valideren

Gebruik het volgende argument met de microsoft Defender Antivirus command-line utility () om te controleren of uw netwerk kan communiceren met de `mpcmdrun.exe` Microsoft Defender Antivirus-cloudservice:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> U moet een versie op beheerdersniveau van de opdrachtprompt openen. Klik met de rechtermuisknop op het item in het menu Start, klik op **Uitvoeren als beheerder** en klik op **Ja** bij de machtigingenprompt. Deze opdracht werkt alleen in Windows 10, versie 1703 of hoger.

Zie Microsoft Defender Antivirus beheren met het mpcmdrun.exe [commandline-hulpprogramma voor meer informatie.](command-line-arguments-microsoft-defender-antivirus.md)

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a>Poging om een nep-malwarebestand van Microsoft te downloaden

U kunt een voorbeeldbestand downloaden dat door Microsoft Defender Antivirus wordt gedetecteerd en geblokkeerd als u goed verbonden bent met de cloud.

Download het bestand door naar [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .

> [!NOTE]
> Dit bestand is geen echt stukje malware. Het is een nepbestand dat is ontworpen om te testen of u goed verbonden bent met de cloud.

Als u goed bent verbonden, ziet u een waarschuwingsmelding voor Microsoft Defender Antivirus.

Als u Microsoft Edge gebruikt, ziet u ook een meldingsbericht:

:::image type="content" source="../../media/wdav-bafs-edge.png" alt-text="Schermafbeelding van de melding dat malware is gevonden in Edge":::

Een soortgelijk bericht treedt op als u Internet Explorer gebruikt:

:::image type="content" source="../../media/wdav-bafs-ie.png" alt-text="Microsoft Defender AV-melding dat malware is gevonden":::

U ziet ook een detectie onder In **quarantaine** geplaatste bedreigingen in de sectie **Scangeschiedenis** in de Windows Security-app:

1. Open de Windows Security-app door op het schildpictogram op de taakbalk te klikken of door te zoeken in het startmenu voor **Beveiliging.**

2. Selecteer **Virusbeveiliging & en** selecteer vervolgens **Beschermingsgeschiedenis.**

3. Selecteer onder **de sectie In quarantaine geplaatste** bedreigingen de optie Volledige geschiedenis **bekijken** om de gedetecteerde nep-malware te zien.

   > [!NOTE]
   > Versies van Windows 10 vóór versie 1703 hebben een andere gebruikersinterface. Zie [Microsoft Defender Antivirus in de Windows Security-app](microsoft-defender-security-center-antivirus.md).

   In het Windows-gebeurtenislogboek wordt ook [Windows Defender-clientgebeurtenis-id 1116 voor client.](troubleshoot-microsoft-defender-antivirus.md)

