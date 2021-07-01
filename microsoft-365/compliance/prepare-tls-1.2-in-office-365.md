---
title: Voorbereiden op TLS 1.2 in Office 365 en Office 365 GCC
description: Voorbereiden op het gebruik van TLS 1.2 voor alle client-server- en browser-server-combinaties in Office 365 en Office 365 GCC nadat ondersteuning voor TLS 1.0 en 1.1 is uitgeschakeld.
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 331dd1ea510983e57c069f8d142aa0f7d3f7062e
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226081"
---
# <a name="preparing-for-tls-12-in-office-365-and-office-365-gcc"></a>Voorbereiden op TLS 1.2 in Office 365 en Office 365 GCC

## <a name="summary"></a>Samenvatting

Om onze klanten de allerbeste codering te bieden, is Microsoft van plan Transport Layer Security (TLS) versies 1.0 en 1.1 in Office 365 en Office 365 GCC te beëindigen. We begrijpen dat de beveiliging van uw gegevens belangrijk is en we streven naar transparantie met betrekking tot wijzigingen die van invloed kunnen zijn op uw gebruik van de TLS-service.

De [Implementatie van Microsoft TLS 1.0](https://support.microsoft.com/help/3117336/schannel-implementation-of-tls-1-0-in-windows-security-status-update-n) heeft geen bekende beveiligingsproblemen. Maar vanwege mogelijke toekomstige protocoldowngrade-aanvallen en andere TLS-beveiligingsproblemen, beëindigen we de ondersteuning voor TLS 1.0 en 1.1 in Microsoft Office 365 en Office 365 GCC.

Raadpleeg het volgende artikel voor informatie over het verwijderen van TLS 1.0- en 1.1-afhankelijkheden: [Het oplossen van het TLS 1.0 probleem](https://www.microsoft.com/download/details.aspx?id=55266).

## <a name="more-information"></a>Meer informatie

Vanaf januari 2020 zijn we al begonnen met de afschaffing van TLS 1.0 en 1.1. Alle clients, apparaten of services die verbinding maken met Office 365 via TLS 1.0 of 1.1 in onze DoD- of GCC High-exemplaren worden niet ondersteund. Voor onze commerciële klanten van Office 365 begint de intrekking van TLS 1.0 en 1.1 op 15 oktober 2020 en wordt de uitrol in de weken en maanden daarna voortgezet. 

Wij bevelen aan dat alle combinaties van client-server en browserserver TLS 1.2 (of een latere versie) gebruiken om verbinding met Office 365-services te onderhouden. Mogelijk moet u bepaalde combinaties van client-server en browserserver bijwerken.

U moet toepassingen bijwerken die via TLS 1.0 Microsoft 365 TLS 1.1 of TLS 1.1 bellen om TLS 1.2 te gebruiken. .NET 4.5 is standaard ingesteld op TLS 1.1. Zie Transport Layer Security [(TLS) 1.2](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)op clients inschakelen als u uw .NET-configuratie wilt bijwerken.

Van de volgende clients is bekend dat ze TLS 1.2 niet kunnen gebruiken. Werk uw clients bij om ononderbroken toegang tot de service te waarborgen.

- Android 4.3 en eerdere versies
- Firefox versie 5.0 en eerdere versies
- Internet Explorer 8-10 op Windows 7 en eerdere versies
- Internet Explorer 10 op Windows Phone 8
- Safari 6.0.4/OS X10.8.4 en eerdere versies

### <a name="tls-12-for-microsoft-teams-rooms-and-surface-hub"></a>TLS 1.2 voor Microsoft Teams-ruimten en Surface Hub

Microsoft Teams-ruimten (voorheen bekend als Skype Room System V2 SRS V2) ondersteunen TLS 1.2 sinds december 2018. We bevelen aan dat kamer-apparaten de Microsoft Teams-ruimten appversie 4.0.64.0 of hoger hebben geïnstalleerd. Voor meer informatie, raadpleeg de [Opmerkingen bij release](/microsoftteams/room-systems/srs2-release-note). De wijzigingen zijn achterwaarts en voorwaarts compatibel.

Surface Hub heeft in mei 2019 ondersteuning voor TLS 1.2 uitgebracht.

TLS 1.2-ondersteuning voor Microsoft Teams Rooms en Surface Hub-producten vereist ook de volgende codewijzigingen op de server:

- In april 2019 zijn wijzigingen in Skype voor Bedrijven Online-server live doorgevoerd. Skype voor Bedrijven Online ondersteunt nu het verbinden van Microsoft Teams Rooms en Surface Hub-apparaten met behulp van TLS 1.2.
- Klanten van Skype voor Bedrijven Server moeten een cumulatieve update (CU) installeren om TLS 1.2 te gebruiken voor Teams Rooms-systemen en Surface Hub.

  - Voor Skype voor Bedrijven Server 2015 is CU9 al uitgebracht in mei 2019.
  - Voor Skype voor Bedrijven Server 2019 was CU1 eerder gepland voor april 2019, maar is uitgesteld tot juni 2019.

  > [!NOTE]
  > Klanten van Skype voor Bedrijven op locatie mogen TLS 1.0/1.1 niet uitschakelen voordat ze specifieke CU's voor Skype voor Bedrijven Server hebben geïnstalleerd.

Als u een on-premises infrastructuur gebruikt voor hybride scenario's of Active Directory Federation Services, moet u ervoor zorgen dat de infrastructuur zowel binnenkomende als uitgaande verbindingen ondersteunt die TLS 1.2 gebruiken.

## <a name="references"></a>Verwijzingen

De volgende bronnen bieden richtlijnen om ervoor te zorgen dat uw clients TLS 1.2 of een latere versie gebruiken en om TLS 1.0 en 1.1 uit te schakelen.

- Als u Windows 7-clients hebt die verbinding maken met Office 365, moet u ervoor zorgen dat TLS 1.2 het standaard beveiligde protocol is in WinHTTP in Windows. Voor meer informatie raadpleegt u [KB 3140245 - Update om TLS 1.1 en TLS 1.2 in te schakelen als standaard beveiligde protocollen in WinHTTP in Windows](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in).
- [TLS-coderingssuites die worden ondersteund door Office 365](/microsoft-365/compliance/technical-reference-details-about-encryption#tls-cipher-suites-supported-by-office-365)
- Raadpleeg [TLS 1.2-ondersteuning bij Microsoft](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/) om zwak TLS-gebruik te corrigeren door TLS 1.0- en 1.1-afhankelijkheden te verwijderen.
- De [Nieuwe IIS-functionaliteit](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) maakt het gemakkelijker om clients te vinden op [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) en [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) die verbinding maken met de service met behulp van zwakke beveiligingsprotocollen.
- Meer informatie over het oplossen van het [TLS 1.0-probleem.](https://www.microsoft.com/download/details.aspx?id=55266)
- Ga naar [Office 365-vertrouwenscentrum](https://www.microsoft.com/trustcenter/cloudservices/office365) voor algemene informatie over onze aanpak van beveiliging.
- [Voorbereiden op beëindiging van TLS 1.0/1.1 - Office365 Skype voor Bedrijven](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Exchange Server TLS-richtlijnen, deel 1: Voorbereiden op TLS 1.2](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Exchange Server TLS-richtlijnen deel 2: TLS 1.2 inschakelen en klanten identificeren die het niet gebruiken](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Exchange Server TLS-richtlijnen deel 3: TLS 1.0/1.1 uitschakelen](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [Schakel ondersteuning voor TLS 1.1 en TLS 1.2 in Office Online Server in](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)
