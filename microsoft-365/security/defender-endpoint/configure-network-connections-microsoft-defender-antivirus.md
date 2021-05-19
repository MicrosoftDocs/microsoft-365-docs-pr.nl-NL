---
title: Netwerkverbindingen van Microsoft Defender Antivirus configureren en valideren
description: Configureer en test uw verbinding met de Microsoft Defender Antivirus cloudbeveiligingsservice.
keywords: antivirus, Microsoft Defender Antivirus, antimalware, beveiliging, defender, cloud, agressiviteit, beschermingsniveau
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 5e754c2f4b5406d4b91ef624415f3819d3171305
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536020"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Netwerkverbindingen van Microsoft Defender Antivirus configureren en valideren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Als u Microsoft Defender Antivirus beveiliging in de cloud goed wilt laten werken, moet u uw netwerk zo configureren dat verbindingen tussen uw eindpunten en bepaalde Microsoft-servers worden toegestaan. In dit artikel worden de verbindingen vermeld die moeten worden toegestaan, bijvoorbeeld met behulp van firewallregels, en worden instructies gegeven voor het valideren van uw verbinding. Als u uw beveiliging correct configureert, kunt u ervoor zorgen dat u de beste waarde ontvangt van uw beveiligingsservices die in de cloud worden geleverd.

Zie het blogbericht [Belangrijke wijzigingen in het eindpunt van Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) voor meer informatie over netwerkconnectiviteit.

> [!TIP]
> U kunt ook naar de demowebsite [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) van Microsoft Defender voor Eindpunt demo.wd.microsoft.com om te bevestigen dat de volgende functies werken:
>
> - Cloudbeveiliging
> - Snel leren (inclusief blok op het eerste gezicht)
> - Mogelijk ongewenste blokkering van toepassingen

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Verbindingen met de Microsoft Defender Antivirus cloudservice toestaan

De Microsoft Defender Antivirus cloudservice biedt snelle, sterke beveiliging voor uw eindpunten. Het inschakelen van de door de cloud geleverde beveiligingsservice is optioneel, maar het wordt ten zeerste aanbevolen omdat deze belangrijke bescherming biedt tegen malware op uw eindpunten en in uw netwerk.

> [!NOTE]
> De Microsoft Defender Antivirus cloudservice is een mechanisme voor het leveren van bijgewerkte beveiliging voor uw netwerk en eindpunten. Hoewel het een cloudservice wordt genoemd, is het niet alleen beveiliging voor bestanden die zijn opgeslagen in de cloud, maar wordt gebruikgemaakt van gedistribueerde resources en machine learning om uw eindpunten te beschermen tegen een snelheid die veel sneller is dan traditionele beveiligingsinformatie-updates.

Zie [Beveiliging in de cloud](enable-cloud-protection-microsoft-defender-antivirus.md) inschakelen voor meer informatie over het inschakelen van de service met Intune, Microsoft Endpoint Configuration Manager, Groepsbeleid, PowerShell-cmdlets of op afzonderlijke clients in de Windows-beveiliging app. 

Nadat u de service hebt ingeschakeld, moet u mogelijk uw netwerk of firewall configureren om verbindingen tussen de service en uw eindpunten toe te staan.

Omdat uw beveiliging een cloudservice is, moeten computers toegang hebben tot internet en de Microsoft Defender voor Office 365 machine learning-services. Sluit de URL niet uit `*.blob.core.windows.net` van een netwerkcontrole. 

De onderstaande tabel bevat de services en bijbehorende URL's. Zorg ervoor dat er geen firewall- of netwerkfilterregels zijn die toegang tot deze URL's weigeren, of u moet mogelijk een regel voor toestaan speciaal voor hen maken (met uitzondering van de `*.blob.core.windows.net` URL). Hieronder vermelden URL's gebruiken poort 443 voor communicatie.


| **Service**| **Beschrijving** |**URL** |
| :--: | :-- | :-- |
| Microsoft Defender Antivirus door de cloud geleverde beveiligingsservice, ook wel Microsoft Active Protection Service (KAARTEN)|Gebruikt door Microsoft Defender Antivirus om beveiliging in de cloud te bieden|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| Microsoft Update Service (MU) <br/> Windows Updateservice (WU)|  Beveiligingsinformatie en productupdates   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> Zie [Verbindings-eindpunten voor Windows Update voor meer informatie](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|Beveiligingsinformatieupdates Alternatieve downloadlocatie (ADL)|   Alternatieve locatie voor Microsoft Defender Antivirus beveiligingsintelligentieupdates als de geïnstalleerde beveiligingsintelligentie verouderd is (7 of meer dagen achter)|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| Opslag voor malware indienen|Upload locatie voor bestanden die zijn ingediend bij Microsoft via het formulier Voorzending of automatische voorbeeldinzending    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| Intrekkingslijst voor certificaten (CRL)|Gebruikt door Windows bij het maken van de SSL-verbinding met KAARTEN voor het bijwerken van de CRL   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| Symbol Store|Gebruikt door Microsoft Defender Antivirus om bepaalde kritieke bestanden te herstellen tijdens herstelstromen  | `https://msdl.microsoft.com/download/symbols` |
| Universele telemetrieclient| Gebruikt door Windows om diagnostische gegevens van de client te verzenden; Microsoft Defender Antivirus telemetrie gebruikt voor productkwaliteitscontroledoeleinden   | De update gebruikt SSL (TCP-poort 443) om manifesten te downloaden en diagnostische gegevens te uploaden naar Microsoft met de volgende DNS-eindpunten:   `vortex-win.data.microsoft.com` <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>Verbindingen tussen uw netwerk en de cloud valideren

Nadat u de url's hierboven hebt toestaan, kunt u testen of u verbinding hebt met de Microsoft Defender Antivirus-cloudservice en correct gegevens rapporteert en ontvangt om ervoor te zorgen dat u volledig bent beveiligd.

**Gebruik het cmdline-hulpprogramma om beveiliging in de cloud te valideren:**

Gebruik het volgende argument met Microsoft Defender Antivirus command-line utility () om te controleren of uw netwerk kan communiceren met de `mpcmdrun.exe` Microsoft Defender Antivirus cloudservice:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> U moet een versie op beheerdersniveau van de opdrachtprompt openen. Klik met de rechtermuisknop op het item in het menu Start, klik op **Uitvoeren als beheerder** en klik op **Ja** bij de machtigingenprompt. Deze opdracht werkt alleen op Windows 10, versie 1703 of hoger.

Zie De Microsoft Defender Antivirus [beheren mpcmdrun.exe opdrachtregel](command-line-arguments-microsoft-defender-antivirus.md)voor meer informatie.

**Probeer een nep-malwarebestand van Microsoft te downloaden:**

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

1. Open de Windows-beveiliging app door op het schildpictogram in de taakbalk te klikken of door te zoeken in het startmenu voor **Defender.**

2. Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk) en vervolgens het label **Scangeschiedenis:**

    ![Schermafbeelding van het label Geschiedenis scannen in de Windows-beveiliging app](images/defender/wdav-history-wdsc.png)

3. Selecteer onder **de sectie In quarantaine geplaatste** bedreigingen de optie Volledige geschiedenis **bekijken** om de gedetecteerde nep-malware te zien.

   > [!NOTE]
   > Versies van Windows 10 versie 1703 hebben een andere gebruikersinterface. Zie [Microsoft Defender Antivirus in de Windows-beveiliging app](microsoft-defender-security-center-antivirus.md).

   In Windows gebeurtenislogboek wordt ook Windows Defender [clientgebeurtenis-id 1116.](troubleshoot-microsoft-defender-antivirus.md)

## <a name="related-articles"></a>Verwante artikelen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)

- [Cloudbeveiliging inschakelen](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Opdrachtregelargumenten](command-line-arguments-microsoft-defender-antivirus.md)

- [Belangrijke wijzigingen in het eindpunt van Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
