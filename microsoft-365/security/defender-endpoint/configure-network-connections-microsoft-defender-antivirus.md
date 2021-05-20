---
title: Netwerkverbindingen van Microsoft Defender Antivirus configureren en valideren
description: Configureer en test uw verbinding met de Microsoft Defender Antivirus cloudbeveiligingsservice.
keywords: antivirus, Microsoft Defender Antivirus, antimalware, beveiliging, verdediger, wolk, agressiviteit, beschermingsniveau
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
ms.openlocfilehash: ef5a9ffdf45a2f8e7f262ae7f969cd19e848b7a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572523"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Netwerkverbindingen van Microsoft Defender Antivirus configureren en valideren

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Om ervoor te zorgen Microsoft Defender Antivirus cloudbeveiliging goed werkt, moet u uw netwerk configureren om verbindingen tussen uw eindpunten en bepaalde Microsoft-servers mogelijk te maken. In dit artikel worden de verbindingen weergegeven die moeten worden toegestaan, bijvoorbeeld met behulp van firewallregels, en vindt u instructies voor het valideren van uw verbinding. Door uw beveiliging correct te configureren, zorgt u ervoor dat u de beste waarde ontvangt van uw in de cloud geleverde beveiligingsservices.

Zie de blogpost [Belangrijke wijzigingen in het eindpunt](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) van Microsoft Active Protection Services voor meer informatie over netwerkconnectiviteit.

> [!TIP]
> U kunt ook de demowebsite Microsoft Defender for Endpoint bezoeken op [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) om te bevestigen dat de volgende functies werken:
>
> - Cloudbeveiliging
> - Snel leren (inclusief blok op het eerste gezicht)
> - Mogelijk ongewenste applicatieblokkering

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Verbindingen met de Microsoft Defender Antivirus cloudservice toestaan

De Microsoft Defender Antivirus cloudservice biedt snelle, sterke bescherming voor uw eindpunten. Het inschakelen van de cloudbeveiligingsservice is optioneel, maar wordt ten zeerste aanbevolen omdat deze belangrijke bescherming biedt tegen malware op uw eindpunten en in uw netwerk.

> [!NOTE]
> De Microsoft Defender Antivirus cloudservice is een mechanisme voor het leveren van bijgewerkte beveiliging aan uw netwerk en eindpunten. Hoewel het een cloudservice wordt genoemd, is het niet alleen bescherming voor bestanden die in de cloud zijn opgeslagen, maar maakt het gebruik van gedistribueerde bronnen en machine learning om bescherming te bieden aan uw eindpunten met een snelheid die veel sneller is dan traditionele updates voor beveiligingsintelligentie.

Zie [Cloudbeveiliging inschakelen](enable-cloud-protection-microsoft-defender-antivirus.md) voor meer informatie over het inschakelen van de service met Intune, Microsoft Endpoint Configuration Manager, Groepsbeleid, PowerShell-cmdlets of voor afzonderlijke clients in de Windows-beveiliging-app. 

Nadat u de service hebt ingeschakeld, moet u mogelijk uw netwerk of firewall configureren om verbindingen tussen deze netwerk en uw eind punten toe te staan.

Omdat uw beveiliging een cloudservice is, moeten computers toegang hebben tot internet en de Microsoft Defender bereiken voor Office 365 machine learning-services. Sluit de URL niet `*.blob.core.windows.net` uit van enige vorm van netwerkinspectie. 

In de onderstaande tabel vindt u een overzicht van de services en de bijbehorende URL's. Zorg ervoor dat er geen firewall- of netwerkfilterregels zijn die de toegang tot deze URL's weigeren, of dat u mogelijk een toegestane regel moet maken die specifiek voor hen is bedoeld (met uitzondering van de URL `*.blob.core.windows.net` ). Hieronder vermelden URL's gebruiken poort 443 voor communicatie.


| **Service**| **Beschrijving** |**URL** |
| :--: | :-- | :-- |
| Microsoft Defender Antivirus cloud-geleverde beveiligingsservice, ook wel Microsoft Active Protection Service (MAPS) genoemd|Gebruikt door Microsoft Defender Antivirus om cloud-geleverde bescherming te bieden|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| Microsoft Update Service (MU) <br/> Windows Updateservice (WU)|  Beveiligingsinformatie en productupdates   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> Zie [Verbindingseindpunten voor Windows update voor](/windows/privacy/manage-windows-1709-endpoints#windows-update) meer informatie|
|Beveiligingsinformatie werkt alternatieve downloadlocatie (ADL) bij|   Alternatieve locatie voor Microsoft Defender Antivirus updates van beveiligingsintelligentie als de geïnstalleerde beveiligingsinformatie verouderd is (7 of meer dagen achter)|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| Opslag van malware-indiening|Upload locatie voor bestanden die bij Microsoft zijn ingediend via het indieningsformulier of automatische voorbeeldinzending    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| Certificaatintrekkingslijst (CRL)|Gebruikt door Windows bij het maken van de SSL-verbinding met MAPS voor het bijwerken van de CRL   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| Symbool winkel|Gebruikt door Microsoft Defender Antivirus om bepaalde kritieke bestanden te herstellen tijdens herstelstromen  | `https://msdl.microsoft.com/download/symbols` |
| Universele telemetrieclient| Gebruikt door Windows om diagnostische gegevens van klanten te verzenden; Microsoft Defender Antivirus gebruikt telemetrie voor productkwaliteitsbewakingsdoeleinden   | De update maakt gebruik van SSL (TCP Port 443) om manifesten te downloaden en diagnostische gegevens te uploaden naar Microsoft die de volgende DNS-eindpunten gebruikt:   `vortex-win.data.microsoft.com` <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>Verbindingen tussen uw netwerk en de cloud valideren

Nadat u de bovenstaande URL's hebt toegestond, kunt u testen of u bent verbonden met de Microsoft Defender Antivirus cloudservice en informatie correct rapporteert en ontvangt om ervoor te zorgen dat u volledig beschermd bent.

**Gebruik de cmdline-tool om door de cloud geleverde beveiliging te valideren:**

Gebruik het volgende argument met het hulpprogramma Microsoft Defender Antivirus opdrachtregel ( `mpcmdrun.exe` ) om te controleren of uw netwerk kan communiceren met de Microsoft Defender Antivirus cloudservice:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> U moet een versie op beheerdersniveau van de opdrachtprompt openen. Klik met de rechtermuisknop op het item in het menu Start, klik op **Uitvoeren als beheerder** en klik op **Ja** bij de prompt machtigingen. Deze opdracht werkt alleen op Windows 10, versie 1703 of hoger.

Zie [Microsoft Defender Antivirus beheren met het opdrachtregelprogramma mpcmdrun.exe](command-line-arguments-microsoft-defender-antivirus.md)voor meer informatie.

**Probeer een nep-malwarebestand van Microsoft te downloaden:**

U kunt een voorbeeldbestand downloaden dat Microsoft Defender Antivirus detecteert en blokkeert als u goed verbonden bent met de cloud.

Download het bestand door naar [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .

> [!NOTE]
> Dit bestand is geen echt stuk malware. Het is een nepbestand dat is ontworpen om te testen of je goed verbonden bent met de cloud.

Als u goed verbonden bent, ziet u een waarschuwing Microsoft Defender Antivirus melding.

Als u Microsoft Edge gebruikt, ziet u ook een meldingsbericht:

![Microsoft Edge de gebruiker te informeren dat malware is gevonden](images/defender/wdav-bafs-edge.png)

Een soortgelijk bericht treedt op als u Internet Explorer gebruikt:

![Microsoft Defender Antivirus melding om de gebruiker te informeren dat malware is gevonden](images/defender/wdav-bafs-ie.png)

U ziet ook een detectie onder **Bedreigingen** in quarantaine in de sectie **Scangeschiedenis** in de Windows-beveiliging-app:

1. Open de Windows-beveiliging app door op het schildpictogram in de taakbalk te klikken of in het startmenu te zoeken naar **Beveiliging**.

2. Selecteer **Virus & bedreigingsbeveiliging** en selecteer vervolgens **Beveiligingsgeschiedenis**.

3. Selecteer onder de sectie **In quarantaine geplaatste bedreigingen** de optie **Volledige geschiedenis bekijken** om de gedetecteerde valse malware te zien.

   > [!NOTE]
   > Versies van Windows 10 voor versie 1703 hebben een andere gebruikersinterface. Zie [Microsoft Defender Antivirus in de Windows-beveiliging-app](microsoft-defender-security-center-antivirus.md).

   In het Windows gebeurtenislogboek wordt ook [Windows Defender clientgebeurtenis-ID 1116 weergegeven.](troubleshoot-microsoft-defender-antivirus.md)

## <a name="related-articles"></a>Verwante artikelen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)

- [Cloudbeveiliging inschakelen](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Opdrachtregelargumenten](command-line-arguments-microsoft-defender-antivirus.md)

- [Belangrijke wijzigingen in het eindpunt van Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
