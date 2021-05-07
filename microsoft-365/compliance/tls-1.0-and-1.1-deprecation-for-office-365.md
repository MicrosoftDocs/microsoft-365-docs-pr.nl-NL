---
title: TLS 1.0 en 1.1 uitschakelen voor Microsoft 365
description: Beschrijft TLS 1.0 en 1.1 deprecation and disablement for Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 3d44e178d351942b4a178ddc1954ddd839665639
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161959"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a>TLS 1.0 en 1.1 uitschakelen voor Microsoft 365

> [!IMPORTANT]
> We hebben de uitzetting van TLS 1.0 en 1.1 tijdelijk stopgezet voor commerciële klanten vanwege COVID-19. Aangezien supply chains zijn aangepast en bepaalde landen een back-up openen, hebben we de implementatie van TLS 1.2 enforcement op 15 oktober 2020 opnieuw opgestart. De uitrol gaat de komende weken en maanden door.

Vanaf 31 oktober 2018 worden de TLS-protocollen Transport Layer Security (TLS) 1.0 en 1.1 afgeschaft voor de Microsoft 365 service. Het effect voor eindgebruikers is minimaal. Deze wijziging is meer dan twee jaar openbaar gemaakt, met de eerste openbare aankondiging in december 2017. Dit artikel is alleen bedoeld voor de Office 365 lokale client met betrekking tot de Office 365-service, maar kan ook van toepassing zijn op on-premises TLS-problemen met Office en Office Online Server/Office Web Apps.

Voor SharePoint en OneDrive moet u .NET bijwerken en configureren om TLS 1.2 te ondersteunen. Zie [TLS 1.2 inschakelen](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)op clients voor meer informatie.

## <a name="office-365-and-tls-overview"></a>Office 365 en TLS-overzicht

De Office client is afhankelijk van de Windows webservice (WINHTTP) voor het verzenden en ontvangen van verkeer via TLS-protocollen. De Office client kan TLS 1.2 gebruiken als de webservice van de lokale computer TLS 1.2 kan gebruiken. Alle Office-clients kunnen TLS-protocollen gebruiken, omdat TLS- en SSL-protocollen deel uitmaken van het besturingssysteem en niet specifiek zijn voor de Office client.

### <a name="on-windows-8-and-later-versions"></a>Op Windows 8 en latere versies

Standaard zijn de TLS 1.2- en 1.1-protocollen beschikbaar als er geen netwerkapparaten zijn geconfigureerd om TLS 1.2-verkeer te weigeren.

### <a name="on-windows-7"></a>Op Windows 7

TLS 1.1- en 1.2-protocollen zijn niet beschikbaar zonder de [KB 3140245-update.](https://support.microsoft.com/help/3140245) De update lost dit probleem op en voegt de volgende register subsleutel toe:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Windows 7 gebruikers die deze update niet hebben, worden beïnvloed vanaf 31 oktober 2018. [KB 3140245](https://support.microsoft.com/help/3140245) heeft informatie over het wijzigen van WINHTTP-instellingen om TLS-protocollen in te stellen.

#### <a name="more-information"></a>Meer informatie

De waarde van de **registersleutel DefaultSecureProtocols** die in het KB-artikel wordt beschreven, bepaalt welke netwerkprotocollen kunnen worden gebruikt:

|StandaardSecureProtocols-waarde|Protocol ingeschakeld|
|-|-|
|0x00000008|Standaard SSL 2.0 inschakelen|
|0x00000020|Standaard SSL 3.0 inschakelen|
|0x00000080|Standaard TLS 1.0 inschakelen|
|0x00000200|Standaard TLS 1.1 inschakelen|
|0x00000800|Standaard TLS 1.2 inschakelen|

## <a name="office-clients-and-tls-registry-keys"></a>Office clients en TLS-registersleutels

U kunt verwijzen naar [KB 4057306 Voorbereidingen](https://support.microsoft.com/help/4057306)treffen voor het verplichte gebruik van TLS 1.2 in Office 365. Dit is een algemeen artikel voor IT-beheerders en het is officiële documentatie over de wijziging van TLS 1.2.

In de volgende tabel ziet u de juiste registersleutelwaarden in Office 365 clients na 31 oktober 2018.

|Ingeschakelde protocollen voor Office 365 service na 31 oktober 2018|Hexadecimale waarde|
|-|-|
|TLS 1.0 + 1,1 + 1,2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1,2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> Gebruik de SSL 2.0- en 3.0-protocollen niet, die ook kunnen worden ingesteld met de **defaultsecureProtocols-toets.** SSL 2.0 en 3.0 worden beschouwd als verouderde en onveilige protocollen. De beste manier is om het gebruik van SSL 2.0 en SSL 3.0 te beëindigen, hoewel de beslissing om dit te doen uiteindelijk afhangt van wat het beste aan uw productbehoeften voldoet. Zie [KB 3009008](https://support.microsoft.com/help/3009008)voor meer informatie over SSL 3.0-beveiligingslekken.

U kunt de standaardinstelling Windows rekenmachine in de programmeermodus gebruiken om dezelfde registersleutelwaarden voor verwijzingen in te stellen. Zie KB 3140245 Update voor het inschakelen van [TLS 1.1 en TLS 1.2](https://support.microsoft.com/help/3140245)als standaardveilige protocollen in WinHTTP in Windows.

Ongeacht of de Windows 7-update[(KB 3140245)](https://support.microsoft.com/help/3140245)is geïnstalleerd of niet, is de register subsleutel DefaultSecureProtocols niet aanwezig en moet deze handmatig of via een groepsbeleidsobject (GPO) worden toegevoegd. Tenzij u moet aanpassen welke veilige protocollen zijn ingeschakeld of beperkt, is deze sleutel niet vereist. U hebt alleen de update Windows 7 SP1[(KB 3140245)](https://support.microsoft.com/help/3140245)nodig.

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a>De .NET Framework bijwerken en configureren voor ondersteuning van TLS 1.2

U moet toepassingen bijwerken die via TLS 1.0 Microsoft 365 TLS 1.1 of TLS 1.1 bellen om TLS 1.2 te gebruiken. .NET 4.5 is standaard ingesteld op TLS 1.1. Zie Transport Layer Security [(TLS) 1.2](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)op clients inschakelen als u uw .NET-configuratie wilt bijwerken.

## <a name="more-information"></a>Meer informatie

Zie Voorbereiden op het verplichte gebruik van [TLS 1.2 in](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)Office 365.